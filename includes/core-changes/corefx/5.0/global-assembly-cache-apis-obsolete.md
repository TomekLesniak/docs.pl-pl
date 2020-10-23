---
ms.openlocfilehash: 959d8cb6d3e52916f6777054f3e9b327dc8edb4e
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434961"
---
### <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="24c5f-101">Interfejsy API pamięci podręcznej zestawów globalnych są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="24c5f-101">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="24c5f-102">Programy .NET Core i .NET 5,0 i nowsze wersje eliminują koncepcję globalnej pamięci podręcznej zestawów (GAC), która była obecna w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24c5f-102">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="24c5f-103">W związku z tym wszystkie interfejsy API platformy .NET Core i .NET 5 +, które zajmują się niepowodzeniem lub nie wykonują operacji.</span><span class="sxs-lookup"><span data-stu-id="24c5f-103">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="24c5f-104">Aby ułatwić przekierowania deweloperów z tych interfejsów API, niektóre interfejsy API związane z GAC są oznaczone jako przestarzałe i generują `SYSLIB0005` ostrzeżenie w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="24c5f-104">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="24c5f-105">Te interfejsy API mogą zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="24c5f-105">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="24c5f-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="24c5f-106">Change description</span></span>

<span data-ttu-id="24c5f-107">Następujące interfejsy API są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="24c5f-107">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="24c5f-108">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="24c5f-108">API</span></span> | <span data-ttu-id="24c5f-109">Oznaczone jako przestarzałe w...</span><span class="sxs-lookup"><span data-stu-id="24c5f-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="24c5f-110">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="24c5f-110">5.0 RC1</span></span> |

<span data-ttu-id="24c5f-111">W .NET Framework 2. x-4. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość zwraca, `true` Jeśli zestaw zapytania został załadowany z pamięci podręcznej, a `false` Jeśli został załadowany z innej lokalizacji na dysku.</span><span class="sxs-lookup"><span data-stu-id="24c5f-111">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="24c5f-112">W programie .NET Core 2. x-3. x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> zawsze zwraca `false` , odzwierciedlające, że pamięć podręczna nie istnieje w programie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="24c5f-112">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="24c5f-113">W programie .NET 5,0 i jego nowszych wersjach <xref:System.Reflection.Assembly.GlobalAssemblyCache> Właściwość nadal zawsze zwraca wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="24c5f-113">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="24c5f-114">Jednak metoda pobierająca właściwość jest również oznaczona jako przestarzała, aby wskazać wywołujący, że powinni przestać uzyskiwać dostęp do właściwości.</span><span class="sxs-lookup"><span data-stu-id="24c5f-114">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="24c5f-115">Biblioteki i aplikacje nie powinny używać <xref:System.Reflection.Assembly.GlobalAssemblyCache> interfejsu API do wprowadzania informacji o zachowaniu w czasie wykonywania, ponieważ zawsze są zwracane `false` w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="24c5f-115">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="24c5f-116">Jest to zmiana tylko w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="24c5f-116">This is a compile-time only change.</span></span> <span data-ttu-id="24c5f-117">Nie ma żadnej zmiany w czasie wykonywania z poprzednich wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="24c5f-117">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="24c5f-118">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="24c5f-118">Reason for change</span></span>

<span data-ttu-id="24c5f-119">Globalna pamięć podręczna zestawów (GAC) nie istnieje jako koncepcja w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="24c5f-119">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="24c5f-120">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="24c5f-120">Version introduced</span></span>

<span data-ttu-id="24c5f-121">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="24c5f-121">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="24c5f-122">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="24c5f-122">Recommended action</span></span>

- <span data-ttu-id="24c5f-123">Jeśli aplikacja wysyła zapytanie do <xref:System.Reflection.Assembly.GlobalAssemblyCache> właściwości, należy rozważyć usunięcie wywołania.</span><span class="sxs-lookup"><span data-stu-id="24c5f-123">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="24c5f-124">Jeśli używasz wartości, <xref:System.Reflection.Assembly.GlobalAssemblyCache> Aby wybrać między "zestaw w pamięci GAC"-Flow a "zestawem, który nie znajduje się w przepływie GAC w czasie wykonywania, należy rozważyć, czy przepływ nadal ma sens dla aplikacji .NET Core, jak i .NET 5.0 +.</span><span class="sxs-lookup"><span data-stu-id="24c5f-124">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="24c5f-125">Jeśli musisz nadal używać przestarzałych interfejsów API, możesz pominąć `SYSLIB0005` ostrzeżenie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="24c5f-125">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="24c5f-126">Możesz również pominąć ostrzeżenie w pliku projektu, co spowoduje wyłączenie ostrzeżenia dla wszystkich plików źródłowych w projekcie.</span><span class="sxs-lookup"><span data-stu-id="24c5f-126">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="24c5f-127">Pomijanie `SYSLIB0005` powoduje wyłączenie tylko <xref:System.Reflection.Assembly.GlobalAssemblyCache> ostrzeżenia obsoletion.</span><span class="sxs-lookup"><span data-stu-id="24c5f-127">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="24c5f-128">Nie wyłącza żadnych innych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="24c5f-128">It does not disable any other warnings.</span></span>

#### <a name="category"></a><span data-ttu-id="24c5f-129">Kategoria</span><span class="sxs-lookup"><span data-stu-id="24c5f-129">Category</span></span>

<span data-ttu-id="24c5f-130">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="24c5f-130">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="24c5f-131">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="24c5f-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
