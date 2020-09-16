---
title: x:Member — dyrektywa
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: 1c5b26b405e574290af54b29b22fb5e19e4b6b95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548250"
---
# <a name="xmember-directive"></a><span data-ttu-id="26154-102">x:Member — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="26154-102">x:Member Directive</span></span>
<span data-ttu-id="26154-103">Deklaruje element członkowski języka XAML w znaczniku.</span><span class="sxs-lookup"><span data-stu-id="26154-103">Declares a XAML member in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="26154-104">Użycie elementu obiektu języka XAML</span><span class="sxs-lookup"><span data-stu-id="26154-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="26154-105">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="26154-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="26154-106">Nazwa klasy zapasowej lub klasy częściowej dla produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`memberName`|<span data-ttu-id="26154-107">Nazwa elementu członkowskiego zdefiniowanej właściwości.</span><span class="sxs-lookup"><span data-stu-id="26154-107">Member name of the property being defined.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26154-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="26154-108">Remarks</span></span>

<span data-ttu-id="26154-109">W implementacji usług platformy .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-109">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="26154-110">`x:Member` nie ma bezpośredniego typu zapasowego, ale jest obsługiwany przez <xref:System.Windows.Markup.MemberDefinition> klasę.</span><span class="sxs-lookup"><span data-stu-id="26154-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="26154-111">W strumieniu węzła XAML `x:Member` element jest reprezentowany jako element członkowski o nazwie `Member` , z przestrzeni nazw XAML języka XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="26154-112">Składowa `Member` zawiera atrybuty zadeklarowane przez znacznik.</span><span class="sxs-lookup"><span data-stu-id="26154-112">The member `Member` holds attributes as declared by markup.</span></span>

<span data-ttu-id="26154-113">Znaczenie `Name` i `Type` nie są przypisane na poziomie usług .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-113">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="26154-114">Są one przechowywane w początkowym strumieniu węzła XAML jako wartości ciągów, które mają być interpretowane później w ramach reguł, które mogą zostać nałożone przez określone struktury.</span><span class="sxs-lookup"><span data-stu-id="26154-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="26154-115">Znaczenie może być wyrównane do nazwy XAML i typu XAML lub może być prawidłowe tylko w systemie typu zapasowego, w zależności od implementacji.</span><span class="sxs-lookup"><span data-stu-id="26154-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="26154-116">Aby obsłużyć praktyczne użycie `x:Members` jako środek do określenia definicji elementów członkowskich w znaczniku, elementy członkowskie muszą być skojarzone z klasą, która może być modyfikowana.</span><span class="sxs-lookup"><span data-stu-id="26154-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="26154-117">Zamierzony model `x:Members` istnieje jako element członkowski typu, który określa `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="26154-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="26154-118">Jednak mechanizm kojarzenia typów i elementów członkowskich lub do tworzenia dynamicznych definicji elementów członkowskich nie jest obsługiwany na poziomie usług .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="26154-119">Jest to pozostało do pojedynczych platform, które mają modele aplikacji, które obsługują definicje elementów członkowskich z języka XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="26154-120">Zazwyczaj akcje kompilacji programu MSBUILD, które umożliwiają adiustację i kompilowanie kodu XAML, i integrowanie go z kodem związanym lub wytwarzaniem czystych zestawów z języka XAML, które są niezbędne do obsługi tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="26154-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="26154-121">x:Property Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="26154-121">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="26154-122">W przypadku Windows Workflow Foundation `x:Property` definiuje elementy członkowskie działania niestandardowego składające się całkowicie z języka XAML lub zdefiniowane w języku XAML dynamiczne elementy członkowskie dla projektanta działań z kodem.</span><span class="sxs-lookup"><span data-stu-id="26154-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="26154-123">`x:Class` musi również być określony w elemencie głównym produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="26154-124">Nie jest to wymagane na poziomie usług .NET XAML, ale jest wymagane, gdy produkcja XAML jest ładowana przez akcje kompilacji MSBUILD, które obsługują działania niestandardowe i Windows Workflow Foundation XAML.</span><span class="sxs-lookup"><span data-stu-id="26154-124">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="26154-125">Windows Workflow Foundation nie używa czystej nazwy typu XAML jako zamierzonej wartości `x:Property` `Type` atrybutu, a zamiast tego używa konwencji, która nie jest udokumentowana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="26154-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="26154-126">Aby uzyskać więcej informacji, zobacz [dynamiczne tworzenie](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="26154-126">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
