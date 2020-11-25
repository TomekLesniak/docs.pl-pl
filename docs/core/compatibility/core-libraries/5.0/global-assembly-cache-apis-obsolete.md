---
title: 'Istotna zmiana: interfejsy API pamięci podręcznej zestawów globalnych są przestarzałe'
description: Dowiedz się więcej o istotnej zmianie programu .NET 5,0 w bibliotekach podstawowych platformy .NET, w których interfejsy API, które zajmują się niepowodzeniem lub nie wykonują operacji.
ms.date: 11/01/2020
ms.openlocfilehash: 2f74fccc68b7a925d909938d77578df8ebe8d60d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761556"
---
# <a name="global-assembly-cache-apis-are-obsolete"></a>Interfejsy API pamięci podręcznej zestawów globalnych są przestarzałe

Programy .NET Core i .NET 5,0 i nowsze wersje eliminują koncepcję globalnej pamięci podręcznej zestawów (GAC), która była obecna w .NET Framework. W związku z tym wszystkie interfejsy API platformy .NET Core i .NET 5 +, które zajmują się niepowodzeniem lub nie wykonują operacji.

Aby ułatwić przekierowania deweloperów z tych interfejsów API, niektóre interfejsy API związane z GAC są oznaczone jako przestarzałe i generują `SYSLIB0005` ostrzeżenie w czasie kompilacji. Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.

## <a name="change-description"></a>Zmień opis

Następujące interfejsy API są oznaczone jako przestarzałe.

| Interfejs API | Oznaczone jako przestarzałe w... |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | 5,0 RC1 |

W .NET Framework 2. x-4. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość zwraca, `true` Jeśli zestaw zapytania został załadowany z pamięci podręcznej, a `false` Jeśli został załadowany z innej lokalizacji na dysku. W programie .NET Core 2. x-3. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> zawsze zwraca `false` , odzwierciedlające, że pamięć podręczna nie istnieje w programie .NET Core.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

W programie .NET 5,0 i jego nowszych wersjach <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość nadal zawsze zwraca wartość `false` . Jednak metoda pobierająca właściwość jest również oznaczona jako przestarzała, aby wskazać wywołujący, że powinni przestać uzyskiwać dostęp do właściwości. Biblioteki i aplikacje nie powinny używać <xref:System.Reflection.Assembly.GlobalAssemblyCache> interfejsu API do wprowadzania informacji o zachowaniu w czasie wykonywania, ponieważ zawsze są zwracane `false` w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

Jest to zmiana tylko w czasie kompilacji. Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.

## <a name="reason-for-change"></a>Przyczyna zmiany

Globalna pamięć podręczna zestawów (GAC) nie istnieje jako koncepcja w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

- Jeśli aplikacja wysyła zapytanie do <xref:System.Reflection.Assembly.GlobalAssemblyCache> właściwości, należy rozważyć usunięcie wywołania. Jeśli używasz wartości, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Aby wybrać między "zestaw w pamięci GAC"-Flow a "zestawem, który nie znajduje się w przepływie GAC w czasie wykonywania, należy rozważyć, czy przepływ nadal ma sens dla aplikacji .NET Core, jak i .NET 5.0 +.

- Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0005` ostrzeżenie w kodzie.

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  Pomijanie `SYSLIB0005` powoduje wyłączenie tylko <xref:System.Reflection.Assembly.GlobalAssemblyCache> ostrzeżenia obsoletion. Nie wyłącza żadnych innych ostrzeżeń.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
