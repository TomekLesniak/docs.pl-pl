---
ms.openlocfilehash: 35041a035041fd4ad5402e1bc0dd137a74d4f949
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434932"
---
### <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="b6ee2-101">Interfejsy API komunikacji zdalnej są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="b6ee2-101">Remoting APIs are obsolete</span></span>

<span data-ttu-id="b6ee2-102">Niektóre interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe i generują `SYSLIB0010` ostrzeżenie w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-102">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="b6ee2-103">Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-103">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b6ee2-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="b6ee2-104">Change description</span></span>

<span data-ttu-id="b6ee2-105">Następujące interfejsy API komunikacji zdalnej są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-105">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="b6ee2-106">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="b6ee2-106">API</span></span> | <span data-ttu-id="b6ee2-107">Oznaczone jako przestarzałe w...</span><span class="sxs-lookup"><span data-stu-id="b6ee2-107">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="b6ee2-108">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="b6ee2-108">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="b6ee2-109">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="b6ee2-109">5.0 RC1</span></span> |

<span data-ttu-id="b6ee2-110">W .NET Framework 2. x-4. x, <xref:System.MarshalByRefObject.GetLifetimeService> metody i <xref:System.MarshalByRefObject.InitializeLifetimeService> kontrolują okres istnienia wystąpień związanych z usługami zdalnymi platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-110">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="b6ee2-111">W programie .NET Core 2. x-3. x te metody zawsze generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-111">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="b6ee2-112">W programie .NET 5,0 i jego nowszych wersjach <xref:System.MarshalByRefObject.GetLifetimeService> <xref:System.MarshalByRefObject.InitializeLifetimeService> metody i są oznaczone jako przestarzałe jako ostrzeżenie, ale nadal generują <xref:System.PlatformNotSupportedException> w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-112">In .NET 5.0 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="b6ee2-113">Jest to zmiana tylko w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-113">This is a compile-time only change.</span></span> <span data-ttu-id="b6ee2-114">Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-114">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b6ee2-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="b6ee2-115">Reason for change</span></span>

<span data-ttu-id="b6ee2-116">[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-116">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="b6ee2-117">Umożliwia utworzenie wystąpienia obiektu w innym procesie (potencjalnie nawet na innym komputerze) i współpracującie z tym obiektem, tak jakby był to zwykłe, w trakcie procesu wystąpienie obiektu .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-117">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="b6ee2-118">Infrastruktura komunikacji zdalnej .NET istnieje tylko w .NET Framework 2. x-4. x.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-118">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="b6ee2-119">Programy .NET Core i .NET 5,0 i nowsze wersje nie obsługują komunikacji zdalnej .NET, a interfejsy API komunikacji zdalnej nie istnieją lub zawsze generują wyjątki dla tych środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-119">.NET Core and .NET 5.0 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="b6ee2-120">Aby pomóc w podniesieniu deweloperów do tych interfejsów API, Obsoleting wybrane interfejsy API związane z usługami zdalnymi.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-120">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="b6ee2-121">Te interfejsy API mogą zostać usunięte całkowicie w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-121">These APIs may be removed entirely in a future version of .NET.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b6ee2-122">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b6ee2-122">Version introduced</span></span>

<span data-ttu-id="b6ee2-123">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="b6ee2-123">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b6ee2-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b6ee2-124">Recommended action</span></span>

- <span data-ttu-id="b6ee2-125">Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-125">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="b6ee2-126">Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="b6ee2-126">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="b6ee2-127">Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0010` ostrzeżenie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="b6ee2-128">Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="b6ee2-129">Pomijanie `SYSLIB0010` powoduje wyłączenie tylko ostrzeżeń obsoletion interfejsu API komunikacji zdalnej.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-129">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="b6ee2-130">Nie wyłącza żadnych innych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="b6ee2-130">It does not disable any other warnings.</span></span> <span data-ttu-id="b6ee2-131">Ponadto nie zmienia to stałe zachowanie w czasie wykonywania <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b6ee2-131">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="b6ee2-132">Kategoria</span><span class="sxs-lookup"><span data-stu-id="b6ee2-132">Category</span></span>

<span data-ttu-id="b6ee2-133">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="b6ee2-133">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6ee2-134">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b6ee2-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
