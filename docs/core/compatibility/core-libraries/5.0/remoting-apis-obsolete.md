---
title: 'Istotna zmiana: interfejsy API komunikacji zdalnej są przestarzałe'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których niektóre interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe i generują ostrzeżenie z niestandardowym IDENTYFIKATORem diagnostyki.
ms.date: 11/01/2020
ms.openlocfilehash: 5687b1471028b077674cfd31cb77ce95dc51bef5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761499"
---
# <a name="remoting-apis-are-obsolete"></a>Interfejsy API komunikacji zdalnej są przestarzałe

Niektóre interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe i generują `SYSLIB0010` ostrzeżenie w czasie kompilacji. Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.

## <a name="change-description"></a>Zmień opis

Następujące interfejsy API komunikacji zdalnej są oznaczone jako przestarzałe.

| Interfejs API | Oznaczone jako przestarzałe w... |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | 5,0 RC1 |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | 5,0 RC1 |

W .NET Framework 2. x-4. x, <xref:System.MarshalByRefObject.GetLifetimeService> metody i <xref:System.MarshalByRefObject.InitializeLifetimeService> kontrolują okres istnienia wystąpień związanych z usługami zdalnymi platformy .NET. W programie .NET Core 2. x-3. x te metody zawsze generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.

W programie .NET 5,0 i jego nowszych wersjach <xref:System.MarshalByRefObject.GetLifetimeService> <xref:System.MarshalByRefObject.InitializeLifetimeService> metody i są oznaczone jako przestarzałe jako ostrzeżenie, ale nadal generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

Jest to zmiana tylko w czasie kompilacji. Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.

## <a name="reason-for-change"></a>Przyczyna zmiany

[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia. Umożliwia utworzenie wystąpienia obiektu w innym procesie (potencjalnie nawet na innym komputerze) i współpracującie z tym obiektem, tak jakby był to zwykłe, w trakcie procesu wystąpienie obiektu .NET. Infrastruktura komunikacji zdalnej .NET istnieje tylko w .NET Framework 2. x-4. x. Programy .NET Core i .NET 5,0 i nowsze wersje nie obsługują komunikacji zdalnej .NET, a interfejsy API komunikacji zdalnej nie istnieją lub zawsze generują wyjątki dla tych środowisk uruchomieniowych.

Aby pomóc w podniesieniu deweloperów do tych interfejsów API, Obsoleting wybrane interfejsy API związane z usługami zdalnymi. Te interfejsy API mogą zostać usunięte całkowicie w przyszłej wersji platformy .NET.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

- Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach. Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../../../porting/net-framework-tech-unavailable.md).

- Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0010` ostrzeżenie w kodzie.

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  Pomijanie `SYSLIB0010` powoduje wyłączenie tylko ostrzeżeń obsoletion interfejsu API komunikacji zdalnej. Nie wyłącza żadnych innych ostrzeżeń. Ponadto nie zmienia to stałe zachowanie w czasie wykonywania <xref:System.PlatformNotSupportedException> .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
