---
ms.openlocfilehash: 8198eca5b9c63d9717260b71ac6687dbf7245f35
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159560"
---
### <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a><span data-ttu-id="09ea3-101">Tworzenie wystąpienia domyślnych metod abstrakcyjnych nie jest obsługiwane</span><span class="sxs-lookup"><span data-stu-id="09ea3-101">Instantiating default implementations of cryptographic abstractions is not supported</span></span>

<span data-ttu-id="09ea3-102">Przeciążenia bez parametrów `Create()` dla abstrakcji kryptograficznej są przestarzałe jako ostrzeżenie dotyczące programu .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="09ea3-102">The parameterless `Create()` overloads on cryptographic abstractions are obsolete as warning as of .NET 5.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="09ea3-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="09ea3-103">Change description</span></span>

<span data-ttu-id="09ea3-104">W .NET Framework 2,0-4,8, abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> można skonfigurować w taki sposób, aby zwracały różne algorytmy.</span><span class="sxs-lookup"><span data-stu-id="09ea3-104">In .NET Framework 2.0 - 4.8, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> can be configured to return different algorithms.</span></span> <span data-ttu-id="09ea3-105">Na przykład w przypadku domyślnej instalacji .NET Framework 4,8, bez parametrów metoda statyczna <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> zwraca wystąpienie algorytmu SHA1, jak pokazano w poniższym fragmencie kodu.</span><span class="sxs-lookup"><span data-stu-id="09ea3-105">For example, on a default install of .NET Framework 4.8, the parameterless, static method <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> returns an instance of the SHA1 algorithm, as shown in the following snippet.</span></span>

<span data-ttu-id="09ea3-106">**Tylko .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="09ea3-106">**.NET Framework only**</span></span>

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

<span data-ttu-id="09ea3-107">Można również użyć [konfiguracji dla całego komputera](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) , aby zmienić domyślny algorytm bez konieczności wywoływania `CryptoConfig` programistycznie.</span><span class="sxs-lookup"><span data-stu-id="09ea3-107">You can also use [machine-wide configuration](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) to change the default algorithm without needing to call into `CryptoConfig` programmatically.</span></span>

<span data-ttu-id="09ea3-108">W programie .NET Core 2,0-3,1 abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> zawsze generują <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="09ea3-108">In .NET Core 2.0 - 3.1, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> always throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="09ea3-109">W programie .NET 5,0 i nowszych wersjach abstrakcyjne kryptograficzne fabryki pierwotne, takie jak <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> są oznaczone jako przestarzałe i generują ostrzeżenie w czasie kompilacji o identyfikatorze `SYSLIB0007` .</span><span class="sxs-lookup"><span data-stu-id="09ea3-109">In .NET 5.0 and later versions, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> are marked obsolete and produce a compile-time warning with ID `SYSLIB0007`.</span></span> <span data-ttu-id="09ea3-110">W czasie wykonywania te metody nadal generują <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="09ea3-110">At run time, these methods continue to throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="09ea3-111">Jest to zmiana tylko w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="09ea3-111">This is a compile-time only change.</span></span> <span data-ttu-id="09ea3-112">Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09ea3-112">There is no run-time change from previous versions of .NET Core.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="09ea3-113">Tylko przeciążenia bezparametryczne `Create()` metod są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="09ea3-113">Only the parameterless overloads of the `Create()` methods are obsolete.</span></span> <span data-ttu-id="09ea3-114">Sparametryzowane przeciążenia nie są przestarzałe i nadal działają zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="09ea3-114">Parameterized overloads are not obsolete and still function as expected.</span></span>
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - <span data-ttu-id="09ea3-115">Przeciążenia bez parametrów *określonych* rodzin algorytmów (nieabstrakcyjne) nie są przestarzałe i będą nadal działać zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="09ea3-115">Parameterless overloads of *specific* algorithm families (not abstractions) are not obsolete, and will continue to function as expected.</span></span>
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

#### <a name="reason-for-change"></a><span data-ttu-id="09ea3-116">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="09ea3-116">Reason for change</span></span>

<span data-ttu-id="09ea3-117">System konfiguracji kryptograficznej obecny w .NET Framework nie jest już obecny w oprogramowaniu .NET Core i .NET 5.0 +, ponieważ starszy system nie pozwala na prawidłową elastyczność kryptograficzną.</span><span class="sxs-lookup"><span data-stu-id="09ea3-117">The cryptographic configuration system present in .NET Framework is no longer present in .NET Core and .NET 5.0+, since that legacy system doesn't allow for proper cryptographic agility.</span></span> <span data-ttu-id="09ea3-118">. Wymagania dotyczące zgodności z poprzednimi wersjami w sieci również uniemożliwiają platformie aktualizowanie niektórych kryptograficznych interfejsów API, aby zachować z wyprzedzeniem kryptografii.</span><span class="sxs-lookup"><span data-stu-id="09ea3-118">.NET's backward-compatibility requirements also prohibit the framework from updating certain cryptographic APIs to keep up with advances in cryptography.</span></span> <span data-ttu-id="09ea3-119">Na przykład <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> Metoda została wprowadzona w .NET Framework 1,0, gdy algorytm wyznaczania wartości skrótu SHA-1 był stanem kompozycji.</span><span class="sxs-lookup"><span data-stu-id="09ea3-119">For example, the <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> method was introduced in .NET Framework 1.0, when the SHA-1 hash algorithm was state-of-the-art.</span></span> <span data-ttu-id="09ea3-120">Minęło dwadzieścia lat, a teraz Algorytm SHA-1 jest traktowany jako uszkodzony, ale nie można zmienić <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> w taki sposób, aby zwracał inny algorytm.</span><span class="sxs-lookup"><span data-stu-id="09ea3-120">Twenty years have passed, and now SHA-1 is considered broken, but we cannot change <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> to return a different algorithm.</span></span> <span data-ttu-id="09ea3-121">Wykonanie tej operacji spowodowałoby nieakceptowalną zmianę w korzystaniu z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="09ea3-121">Doing so would introduce an unacceptable breaking change in consuming applications.</span></span>

<span data-ttu-id="09ea3-122">Najlepszym rozwiązaniem jest to, że biblioteki, które używają kryptograficznych elementów podstawowych (takich jak AES, SHA-\* i RSA), powinny mieć pełną kontrolę nad tym, jak zużywają te elementy pierwotne.</span><span class="sxs-lookup"><span data-stu-id="09ea3-122">Best practice dictates that libraries that consume cryptographic primitives (such as AES, SHA-\*, and RSA) should be in full control over how they consume these primitives.</span></span> <span data-ttu-id="09ea3-123">Aplikacje, które wymagają używania w przyszłości, powinny korzystać z bibliotek wyższego poziomu, które zawijają te elementy pierwotne, i dodają możliwości zarządzania kluczami i elastyczność kryptograficzną.</span><span class="sxs-lookup"><span data-stu-id="09ea3-123">Applications that require future-proofing should utilize higher-level libraries that wrap these primitives and add key management and cryptographic agility capabilities.</span></span> <span data-ttu-id="09ea3-124">Te biblioteki są często udostępniane przez środowisko hostingu.</span><span class="sxs-lookup"><span data-stu-id="09ea3-124">These libraries are often provided by the hosting environment.</span></span> <span data-ttu-id="09ea3-125">Przykładem jest [ASP. Biblioteka ochrony danych w sieci](/aspnet/core/security/data-protection/), która obsługuje te problemy w imieniu aplikacji wywołującej.</span><span class="sxs-lookup"><span data-stu-id="09ea3-125">One example is [ASP.NET's Data Protection library](/aspnet/core/security/data-protection/), which handles these concerns on behalf of the calling application.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="09ea3-126">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="09ea3-126">Version introduced</span></span>

<span data-ttu-id="09ea3-127">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="09ea3-127">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="09ea3-128">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="09ea3-128">Recommended action</span></span>

- <span data-ttu-id="09ea3-129">Zalecanym sposobem działania jest zastępowanie wywołań teraz przestarzałych interfejsów API z wywołaniami metod fabrycznych dla określonych algorytmów, na przykład <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="09ea3-129">The recommended course of action is to replace calls to the now-obsolete APIs with calls to factory methods for specific algorithms, for example, <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>.</span></span> <span data-ttu-id="09ea3-130">Zapewnia to pełną kontrolę nad tym, które algorytmy są tworzone.</span><span class="sxs-lookup"><span data-stu-id="09ea3-130">This gives you full control over which algorithms are instantiated.</span></span>

- <span data-ttu-id="09ea3-131">Jeśli chcesz zachować zgodność z istniejącymi ładunkiem wygenerowanymi przez .NET Framework aplikacje, które używają teraz przestarzałych interfejsów API, użyj zamienników sugerowanych w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="09ea3-131">If you need to maintain compatibility with existing payloads generated by .NET Framework apps that use the now-obsolete APIs, use the replacements suggested in the following table.</span></span> <span data-ttu-id="09ea3-132">Tabela zawiera mapowanie od .NET Framework domyślnych algorytmów do ich odpowiedników w architekturze .NET 5 i.</span><span class="sxs-lookup"><span data-stu-id="09ea3-132">The table provides a mapping from .NET Framework default algorithms to their .NET 5+ equivalents.</span></span>

  | <span data-ttu-id="09ea3-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="09ea3-133">.NET Framework</span></span> | <span data-ttu-id="09ea3-134">Zastępowanie zgodne z platformą .NET Core/.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="09ea3-134">.NET Core / .NET 5.0+ compatible replacement</span></span> | <span data-ttu-id="09ea3-135">Uwagi</span><span class="sxs-lookup"><span data-stu-id="09ea3-135">Remarks</span></span> |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | <span data-ttu-id="09ea3-136">Algorytm SHA-1 jest uznawany za przerwany.</span><span class="sxs-lookup"><span data-stu-id="09ea3-136">The SHA-1 algorithm is considered broken.</span></span> <span data-ttu-id="09ea3-137">Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="09ea3-137">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="09ea3-138">Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="09ea3-138">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="09ea3-139">Algorytm HMACSHA1 nie jest odradzany w przypadku większości nowoczesnych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="09ea3-139">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="09ea3-140">Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="09ea3-140">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="09ea3-141">Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="09ea3-141">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="09ea3-142">Algorytm HMACSHA1 nie jest odradzany w przypadku większości nowoczesnych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="09ea3-142">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="09ea3-143">Rozważ użycie silniejszego algorytmu, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="09ea3-143">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="09ea3-144">Aby uzyskać dalsze wskazówki, zapoznaj się z doradcą zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="09ea3-144">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- <span data-ttu-id="09ea3-145">Jeśli musisz kontynuować wywoływanie przestarzałych `Create()` przeciążeń bez parametrów, możesz pominąć `SYSLIB0007` ostrzeżenie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="09ea3-145">If you must continue to call the obsolete parameterless `Create()` overloads, you can suppress the `SYSLIB0007` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  <span data-ttu-id="09ea3-146">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="09ea3-146">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="09ea3-147">Wykonanie tej czynności powoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w ramach projektu.</span><span class="sxs-lookup"><span data-stu-id="09ea3-147">Doing so disables the warning for all source files within the project.</span></span>

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
  > <span data-ttu-id="09ea3-148">Pominięcie `SYSLIB0007` powoduje wyłączenie tylko ostrzeżeń obsoletion dla interfejsów API kryptografii wymienionych w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="09ea3-148">Suppressing `SYSLIB0007` disables only the obsoletion warnings for the cryptography APIs listed here.</span></span> <span data-ttu-id="09ea3-149">Nie wyłącza żadnych innych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="09ea3-149">It does not disable any other warnings.</span></span> <span data-ttu-id="09ea3-150">Ponadto nawet w przypadku pomijania ostrzeżenia te przestarzałe interfejsy API będą nadal <xref:System.PlatformNotSupportedException> zgłaszać w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="09ea3-150">Additionally, even if you suppress the warning, these obsoleted APIs will still throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

#### <a name="category"></a><span data-ttu-id="09ea3-151">Kategoria</span><span class="sxs-lookup"><span data-stu-id="09ea3-151">Category</span></span>

- <span data-ttu-id="09ea3-152">Kryptografia</span><span class="sxs-lookup"><span data-stu-id="09ea3-152">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="09ea3-153">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="09ea3-153">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

-->