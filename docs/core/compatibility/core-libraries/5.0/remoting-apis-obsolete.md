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
# <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="0b5fd-103">Interfejsy API komunikacji zdalnej są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="0b5fd-103">Remoting APIs are obsolete</span></span>

<span data-ttu-id="0b5fd-104">Niektóre interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe i generują `SYSLIB0010` ostrzeżenie w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-104">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="0b5fd-105">Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-105">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="0b5fd-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="0b5fd-106">Change description</span></span>

<span data-ttu-id="0b5fd-107">Następujące interfejsy API komunikacji zdalnej są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-107">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="0b5fd-108">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="0b5fd-108">API</span></span> | <span data-ttu-id="0b5fd-109">Oznaczone jako przestarzałe w...</span><span class="sxs-lookup"><span data-stu-id="0b5fd-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0b5fd-110">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="0b5fd-110">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0b5fd-111">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="0b5fd-111">5.0 RC1</span></span> |

<span data-ttu-id="0b5fd-112">W .NET Framework 2. x-4. x, <xref:System.MarshalByRefObject.GetLifetimeService> metody i <xref:System.MarshalByRefObject.InitializeLifetimeService> kontrolują okres istnienia wystąpień związanych z usługami zdalnymi platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-112">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="0b5fd-113">W programie .NET Core 2. x-3. x te metody zawsze generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-113">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="0b5fd-114">W programie .NET 5,0 i jego nowszych wersjach <xref:System.MarshalByRefObject.GetLifetimeService> <xref:System.MarshalByRefObject.InitializeLifetimeService> metody i są oznaczone jako przestarzałe jako ostrzeżenie, ale nadal generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-114">In .NET 5.0 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="0b5fd-115">Jest to zmiana tylko w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-115">This is a compile-time only change.</span></span> <span data-ttu-id="0b5fd-116">Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-116">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0b5fd-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="0b5fd-117">Reason for change</span></span>

<span data-ttu-id="0b5fd-118">[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-118">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="0b5fd-119">Umożliwia utworzenie wystąpienia obiektu w innym procesie (potencjalnie nawet na innym komputerze) i współpracującie z tym obiektem, tak jakby był to zwykłe, w trakcie procesu wystąpienie obiektu .NET.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-119">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="0b5fd-120">Infrastruktura komunikacji zdalnej .NET istnieje tylko w .NET Framework 2. x-4. x.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-120">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="0b5fd-121">Programy .NET Core i .NET 5,0 i nowsze wersje nie obsługują komunikacji zdalnej .NET, a interfejsy API komunikacji zdalnej nie istnieją lub zawsze generują wyjątki dla tych środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-121">.NET Core and .NET 5.0 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="0b5fd-122">Aby pomóc w podniesieniu deweloperów do tych interfejsów API, Obsoleting wybrane interfejsy API związane z usługami zdalnymi.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-122">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="0b5fd-123">Te interfejsy API mogą zostać usunięte całkowicie w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-123">These APIs may be removed entirely in a future version of .NET.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0b5fd-124">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0b5fd-124">Version introduced</span></span>

<span data-ttu-id="0b5fd-125">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="0b5fd-125">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0b5fd-126">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="0b5fd-126">Recommended action</span></span>

- <span data-ttu-id="0b5fd-127">Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-127">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="0b5fd-128">Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../../../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="0b5fd-128">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="0b5fd-129">Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0010` ostrzeżenie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-129">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="0b5fd-130">Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-130">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="0b5fd-131">Pomijanie `SYSLIB0010` powoduje wyłączenie tylko ostrzeżeń obsoletion interfejsu API komunikacji zdalnej.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-131">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="0b5fd-132">Nie wyłącza żadnych innych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="0b5fd-132">It does not disable any other warnings.</span></span> <span data-ttu-id="0b5fd-133">Ponadto nie zmienia to stałe zachowanie w czasie wykonywania <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="0b5fd-133">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0b5fd-134">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0b5fd-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
