---
title: x:Property — dyrektywa
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: d4294b39ff262198f8082863d23eb6f4edbc7054
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549304"
---
# <a name="xproperty-directive"></a><span data-ttu-id="3a214-102">x:Property — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="3a214-102">x:Property Directive</span></span>

<span data-ttu-id="3a214-103">Deklaruje Właściwość XAML w znaczniku.</span><span class="sxs-lookup"><span data-stu-id="3a214-103">Declares a XAML property in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="3a214-104">Użycie elementu obiektu języka XAML</span><span class="sxs-lookup"><span data-stu-id="3a214-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="3a214-105">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="3a214-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="3a214-106">Nazwa klasy zapasowej lub klasy częściowej dla produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`propertyName`|<span data-ttu-id="3a214-107">Nazwa elementu członkowskiego zdefiniowanej właściwości.</span><span class="sxs-lookup"><span data-stu-id="3a214-107">Member name of the property being defined.</span></span>|
|`propertyType`|<span data-ttu-id="3a214-108">Nazwa typu (lub inny formularz ciągu, specyficzny dla platformy), który określa typ tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="3a214-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3a214-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3a214-109">Remarks</span></span>

<span data-ttu-id="3a214-110">W implementacji usług platformy .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-110">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="3a214-111">`x:Property` nie ma bezpośredniego typu zapasowego, ale jest obsługiwany przez <xref:System.Windows.Markup.PropertyDefinition> klasę.</span><span class="sxs-lookup"><span data-stu-id="3a214-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="3a214-112">W strumieniu węzła XAML `x:Property` element jest reprezentowany jako element członkowski o nazwie `Property` , z przestrzeni nazw XAML języka XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="3a214-113">Składowa zawiera `Property` atrybuty zadeklarowane przez znacznik.</span><span class="sxs-lookup"><span data-stu-id="3a214-113">The member `Property` hold attributes as declared by markup.</span></span>

<span data-ttu-id="3a214-114">Znaczenie `Name` i `Type` nie są przypisane na poziomie usług .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-114">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="3a214-115">Są one przechowywane w początkowym strumieniu węzła XAML jako wartości ciągów, które mają być interpretowane później w ramach reguł, które mogą zostać nałożone przez określone struktury.</span><span class="sxs-lookup"><span data-stu-id="3a214-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="3a214-116">Znaczenie może być wyrównane do nazwy XAML i typu XAML lub może być prawidłowe tylko w systemie typu zapasowego, w zależności od implementacji.</span><span class="sxs-lookup"><span data-stu-id="3a214-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="3a214-117">Aby obsłużyć praktyczne użycie `x:Members` jako środek do określenia definicji elementów członkowskich w znaczniku, elementy członkowskie muszą być skojarzone z klasą, która może być modyfikowana.</span><span class="sxs-lookup"><span data-stu-id="3a214-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="3a214-118">Zamierzony model `x:Members` istnieje jako element członkowski typu, który określa `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="3a214-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="3a214-119">Jednak mechanizm kojarzenia typów i elementów członkowskich lub do tworzenia dynamicznych definicji elementów członkowskich nie jest obsługiwany na poziomie usług .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="3a214-120">Jest to pozostało do pojedynczych platform, które mają modele aplikacji, które obsługują definicje elementów członkowskich z języka XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="3a214-121">Zazwyczaj akcje kompilacji programu MSBUILD, które umożliwiają adiustację i kompilowanie kodu XAML, i integrowanie go z kodem związanym lub wytwarzaniem czystych zestawów z języka XAML, które są niezbędne do obsługi tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="3a214-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="3a214-122">x:Property Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="3a214-122">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="3a214-123">W przypadku Windows Workflow Foundation `x:Property` definiuje elementy członkowskie działania niestandardowego składające się całkowicie z języka XAML lub zdefiniowane w języku XAML dynamiczne elementy członkowskie dla projektanta działań z kodem.</span><span class="sxs-lookup"><span data-stu-id="3a214-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="3a214-124">`x:Class` musi również być określony w elemencie głównym produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="3a214-125">Nie jest to wymagane na poziomie usług .NET XAML, ale jest wymagane, gdy produkcja XAML jest ładowana przez akcje kompilacji MSBUILD, które obsługują działania niestandardowe i Windows Workflow Foundation XAML.</span><span class="sxs-lookup"><span data-stu-id="3a214-125">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="3a214-126">Windows Workflow Foundation nie używa czystej nazwy typu XAML jako zamierzonej wartości `x:Property` `Type` atrybutu, a zamiast tego używa konwencji, która nie jest udokumentowana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="3a214-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="3a214-127">Aby uzyskać więcej informacji, zobacz [dynamiczne tworzenie](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3a214-127">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
