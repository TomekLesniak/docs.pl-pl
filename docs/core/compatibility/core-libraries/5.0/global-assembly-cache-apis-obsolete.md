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
# <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="d7878-103">Interfejsy API pamięci podręcznej zestawów globalnych są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="d7878-103">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="d7878-104">Programy .NET Core i .NET 5,0 i nowsze wersje eliminują koncepcję globalnej pamięci podręcznej zestawów (GAC), która była obecna w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7878-104">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="d7878-105">W związku z tym wszystkie interfejsy API platformy .NET Core i .NET 5 +, które zajmują się niepowodzeniem lub nie wykonują operacji.</span><span class="sxs-lookup"><span data-stu-id="d7878-105">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="d7878-106">Aby ułatwić przekierowania deweloperów z tych interfejsów API, niektóre interfejsy API związane z GAC są oznaczone jako przestarzałe i generują `SYSLIB0005` ostrzeżenie w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="d7878-106">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="d7878-107">Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="d7878-107">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="d7878-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d7878-108">Change description</span></span>

<span data-ttu-id="d7878-109">Następujące interfejsy API są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d7878-109">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="d7878-110">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="d7878-110">API</span></span> | <span data-ttu-id="d7878-111">Oznaczone jako przestarzałe w...</span><span class="sxs-lookup"><span data-stu-id="d7878-111">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="d7878-112">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="d7878-112">5.0 RC1</span></span> |

<span data-ttu-id="d7878-113">W .NET Framework 2. x-4. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość zwraca, `true` Jeśli zestaw zapytania został załadowany z pamięci podręcznej, a `false` Jeśli został załadowany z innej lokalizacji na dysku.</span><span class="sxs-lookup"><span data-stu-id="d7878-113">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="d7878-114">W programie .NET Core 2. x-3. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> zawsze zwraca `false` , odzwierciedlające, że pamięć podręczna nie istnieje w programie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7878-114">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="d7878-115">W programie .NET 5,0 i jego nowszych wersjach <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość nadal zawsze zwraca wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="d7878-115">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="d7878-116">Jednak metoda pobierająca właściwość jest również oznaczona jako przestarzała, aby wskazać wywołujący, że powinni przestać uzyskiwać dostęp do właściwości.</span><span class="sxs-lookup"><span data-stu-id="d7878-116">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="d7878-117">Biblioteki i aplikacje nie powinny używać <xref:System.Reflection.Assembly.GlobalAssemblyCache> interfejsu API do wprowadzania informacji o zachowaniu w czasie wykonywania, ponieważ zawsze są zwracane `false` w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="d7878-117">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="d7878-118">Jest to zmiana tylko w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="d7878-118">This is a compile-time only change.</span></span> <span data-ttu-id="d7878-119">Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7878-119">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d7878-120">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d7878-120">Reason for change</span></span>

<span data-ttu-id="d7878-121">Globalna pamięć podręczna zestawów (GAC) nie istnieje jako koncepcja w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="d7878-121">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d7878-122">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d7878-122">Version introduced</span></span>

<span data-ttu-id="d7878-123">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="d7878-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d7878-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d7878-124">Recommended action</span></span>

- <span data-ttu-id="d7878-125">Jeśli aplikacja wysyła zapytanie do <xref:System.Reflection.Assembly.GlobalAssemblyCache> właściwości, należy rozważyć usunięcie wywołania.</span><span class="sxs-lookup"><span data-stu-id="d7878-125">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="d7878-126">Jeśli używasz wartości, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Aby wybrać między "zestaw w pamięci GAC"-Flow a "zestawem, który nie znajduje się w przepływie GAC w czasie wykonywania, należy rozważyć, czy przepływ nadal ma sens dla aplikacji .NET Core, jak i .NET 5.0 +.</span><span class="sxs-lookup"><span data-stu-id="d7878-126">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="d7878-127">Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0005` ostrzeżenie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d7878-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="d7878-128">Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.</span><span class="sxs-lookup"><span data-stu-id="d7878-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="d7878-129">Pomijanie `SYSLIB0005` powoduje wyłączenie tylko <xref:System.Reflection.Assembly.GlobalAssemblyCache> ostrzeżenia obsoletion.</span><span class="sxs-lookup"><span data-stu-id="d7878-129">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="d7878-130">Nie wyłącza żadnych innych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="d7878-130">It does not disable any other warnings.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d7878-131">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d7878-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
