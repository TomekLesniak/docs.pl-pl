---
title: 'Istotna zmiana: Tworzenie wystąpień domyślnych implementacji abstrakcyjnych nie jest obsługiwane.'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie nie są przestarzałe przeciążenia tworzenia bez parametrów () dla abstrakcji kryptograficznej.
ms.date: 10/16/2020
ms.openlocfilehash: 8ed7d0b72347ec41ec65ccd9e4004266619c84f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761596"
---
# <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a>Tworzenie wystąpienia domyślnych metod abstrakcyjnych nie jest obsługiwane

Przeciążenia bez parametrów `Create()` dla abstrakcji kryptograficznej są przestarzałe jako ostrzeżenie dotyczące programu .net 5,0.

## <a name="change-description"></a>Zmień opis

W .NET Framework 2,0-4,8, abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> można skonfigurować w taki sposób, aby zwracały różne algorytmy. Na przykład w przypadku domyślnej instalacji .NET Framework 4,8, bez parametrów metoda statyczna <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> zwraca wystąpienie algorytmu SHA1, jak pokazano w poniższym fragmencie kodu.

**Tylko .NET Framework**

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

Można również użyć [konfiguracji dla całego komputera](../../../../framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) , aby zmienić domyślny algorytm bez konieczności wywoływania `CryptoConfig` programistycznie.

W programie .NET Core 2,0-3,1 abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> zawsze generują <xref:System.PlatformNotSupportedException> .

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

W programie .NET 5,0 i nowszych wersjach abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> są oznaczone jako przestarzałe i generują ostrzeżenie w czasie kompilacji o identyfikatorze `SYSLIB0007` . W czasie wykonywania te metody nadal generują <xref:System.PlatformNotSupportedException> .

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

Jest to zmiana tylko w czasie kompilacji. Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.

> [!NOTE]
>
> - Tylko przeciążenia bezparametryczne `Create()` metod są przestarzałe. Sparametryzowane przeciążenia nie są przestarzałe i nadal działają zgodnie z oczekiwaniami.
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - Przeciążenia bez parametrów *określonych* rodzin algorytmów (nieabstrakcyjne) nie są przestarzałe i będą nadal działać zgodnie z oczekiwaniami.
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

## <a name="reason-for-change"></a>Przyczyna zmiany

System konfiguracji kryptograficznej obecny w .NET Framework nie jest już obecny w oprogramowaniu .NET Core i .NET 5.0 +, ponieważ starszy system nie pozwala na prawidłową elastyczność kryptograficzną. Wymagania dotyczące zgodności z poprzednimi wersjami platformy .NET uniemożliwiają platformie aktualizowanie niektórych kryptograficznych interfejsów API, aby zachować z wyprzedzeniem kryptografii. Na przykład <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> Metoda została wprowadzona w .NET Framework 1,0, gdy algorytm wyznaczania wartości skrótu SHA-1 był stanem kompozycji. Minęło dwadzieścia lat, a teraz Algorytm SHA-1 jest traktowany jako uszkodzony, ale nie można zmienić <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> w taki sposób, aby zwracał inny algorytm. Wykonanie tej operacji spowodowałoby nieakceptowalną zmianę w korzystaniu z aplikacji.

Najlepszym rozwiązaniem jest to, że biblioteki, które używają kryptograficznych elementów podstawowych (takich jak AES, SHA-* i RSA), powinny mieć pełną kontrolę nad tym, jak zużywają te elementy pierwotne. Aplikacje, które wymagają używania w przyszłości, powinny korzystać z bibliotek wyższego poziomu, które zawijają te elementy pierwotne, i dodają możliwości zarządzania kluczami i elastyczność kryptograficzną. Te biblioteki są często udostępniane przez środowisko hostingu. Przykładem jest [ASP. Biblioteka ochrony danych w sieci](/aspnet/core/security/data-protection/), która obsługuje te problemy w imieniu aplikacji wywołującej.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Zalecanym sposobem działania jest zastępowanie wywołań teraz przestarzałych interfejsów API z wywołaniami metod fabrycznych dla określonych algorytmów, na przykład <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> . Zapewnia to pełną kontrolę nad tym, które algorytmy są tworzone.

- Jeśli chcesz zachować zgodność z istniejącymi ładunkiem wygenerowanymi przez .NET Framework aplikacje, które używają teraz przestarzałych interfejsów API, użyj zamienników sugerowanych w poniższej tabeli. Tabela zawiera mapowanie od .NET Framework domyślnych algorytmów do ich odpowiedników w architekturze .NET 5 i.

  | .NET Framework | Zastępowanie zgodne z platformą .NET Core/.NET 5.0 | Uwagi |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | Algorytm SHA-1 jest uznawany za przerwany. Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe. Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Algorytm HMACSHA1 nie jest odradzany w przypadku większości nowoczesnych aplikacji. Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe. Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Algorytm HMACSHA1 nie jest odradzany w przypadku większości nowoczesnych aplikacji. Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe. Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- Jeśli musisz kontynuować wywoływanie przestarzałych `Create()` przeciążeń bez parametrów, możesz pominąć `SYSLIB0007` ostrzeżenie w kodzie.

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  Możesz również pominąć ostrzeżenie w pliku projektu. Wykonanie tej czynności powoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w ramach projektu.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > Pominięcie `SYSLIB0007` powoduje wyłączenie tylko ostrzeżeń obsoletion dla interfejsów API kryptografii wymienionych w tym miejscu. Nie wyłącza żadnych innych ostrzeżeń. Ponadto nawet w przypadku pomijania ostrzeżenia te przestarzałe interfejsy API będą nadal <xref:System.PlatformNotSupportedException> zgłaszać w czasie wykonywania.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

### Category

- Cryptography

-->
