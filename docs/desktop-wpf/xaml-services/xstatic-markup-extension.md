---
title: x:Static — Rozszerzenie znaczników
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: 634a480b4d7446ed09708f6c91276d1c2f61d4a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551614"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="04be9-102">x:Static — Rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="04be9-102">x:Static Markup Extension</span></span>

<span data-ttu-id="04be9-103">Odwołuje się do dowolnej jednostki kodu statycznej przez wartość, która jest zdefiniowana w sposób zgodny z Common Language Specification (CLS).</span><span class="sxs-lookup"><span data-stu-id="04be9-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="04be9-104">Właściwość statyczna, do której jest przywoływana, może służyć do podania wartości właściwości w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="04be9-105">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="04be9-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="04be9-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="04be9-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="04be9-107">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="04be9-107">Optional.</span></span> <span data-ttu-id="04be9-108">Prefiks, który odwołuje się do zamapowanej, innej niż domyślnej przestrzeni nazw XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="04be9-109">`prefix` jest pokazywany w sposób jawny, ponieważ rzadko odwołują się do właściwości statycznych, które pochodzą z domyślnej przestrzeni nazw XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="04be9-110">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="04be9-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="04be9-111">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="04be9-111">Required.</span></span> <span data-ttu-id="04be9-112">Nazwa typu, który definiuje żądany statyczny element członkowski.</span><span class="sxs-lookup"><span data-stu-id="04be9-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="04be9-113">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="04be9-113">Required.</span></span> <span data-ttu-id="04be9-114">Nazwa żądanego statycznego elementu członkowskiego wartości (stałej, statycznej właściwości, pola lub wartości wyliczenia).</span><span class="sxs-lookup"><span data-stu-id="04be9-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="04be9-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="04be9-115">Remarks</span></span>

<span data-ttu-id="04be9-116">Obiekt kodu, do którego istnieje odwołanie, musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="04be9-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="04be9-117">Stała</span><span class="sxs-lookup"><span data-stu-id="04be9-117">A constant</span></span>
- <span data-ttu-id="04be9-118">Właściwość statyczna</span><span class="sxs-lookup"><span data-stu-id="04be9-118">A static property</span></span>
- <span data-ttu-id="04be9-119">Pole</span><span class="sxs-lookup"><span data-stu-id="04be9-119">A field</span></span>
- <span data-ttu-id="04be9-120">Wartość wyliczenia</span><span class="sxs-lookup"><span data-stu-id="04be9-120">An enumeration value</span></span>

<span data-ttu-id="04be9-121">Określenie innych jednostek kodu, takich jak niestatyczna właściwość, powoduje błąd czasu kompilacji, jeśli kod XAML jest kompilowany, lub wyjątek analizy czasu ładowania XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="04be9-122">Można tworzyć `x:Static` odwołania do pól statycznych lub właściwości, które nie znajdują się w domyślnej przestrzeni nazw XAML dla bieżącego dokumentu XAML, ale wymaga to mapowania prefiksów.</span><span class="sxs-lookup"><span data-stu-id="04be9-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="04be9-123">Przestrzenie nazw XAML są prawie zawsze definiowane w elemencie głównym dokumentu XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="04be9-124">Operacje wyszukiwania dla właściwości statycznych mogą być wykonywane przez usługi .NET XAML i ich czytniki XAML i moduły zapisujące XAML, gdy są uruchamiane przy użyciu domyślnego kontekstu schematu języka XAML.</span><span class="sxs-lookup"><span data-stu-id="04be9-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="04be9-125">Ten kontekst schematu XAML może używać odbicia środowiska CLR w celu dostarczenia wymaganych wartości statycznych dla konstruowania grafu obiektów.</span><span class="sxs-lookup"><span data-stu-id="04be9-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="04be9-126">`typeName`Określona wartość jest w rzeczywistości nazwą typu XAML, a nie nazwą typu CLR, chociaż są one zasadniczo takie same, jak w przypadku korzystania z domyślnego kontekstu schematu XAML lub w przypadku używania wszystkich istniejących platform implementujących język XAML opartych na środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="04be9-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="04be9-127">Należy zachować ostrożność podczas wprowadzania `x:Static` odwołań, które nie są bezpośrednio typu wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="04be9-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="04be9-128">W sekwencji przetwarzania XAML podane wartości z rozszerzenia znacznika nie wywołują dodatkowej konwersji wartości.</span><span class="sxs-lookup"><span data-stu-id="04be9-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="04be9-129">Jest to prawdziwe nawet wtedy `x:Static` , gdy odwołanie tworzy ciąg tekstowy, a konwersja wartości dla wartości atrybutów na podstawie ciągu tekstowego zwykle występuje dla tego konkretnego elementu członkowskiego lub dla jakichkolwiek wartości elementów członkowskich typu zwracanego.</span><span class="sxs-lookup"><span data-stu-id="04be9-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="04be9-130">Składnią atrybutu jest składnia najczęściej używana z tym rozszerzeniem znacznika.</span><span class="sxs-lookup"><span data-stu-id="04be9-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="04be9-131">Token ciągu podany po `x:Static` ciągu identyfikatora jest przypisywany jako <xref:System.Windows.Markup.StaticExtension.Member%2A> wartość źródłowej <xref:System.Windows.Markup.StaticExtension> klasy rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="04be9-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="04be9-132">Istnieją dwa inne użycia kodu XAML, które są technicznie możliwe.</span><span class="sxs-lookup"><span data-stu-id="04be9-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="04be9-133">Jednak te użycia są mniej typowe, ponieważ nie są one niepotrzebnie pełne:</span><span class="sxs-lookup"><span data-stu-id="04be9-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="04be9-134">Składnia elementu obiektu.</span><span class="sxs-lookup"><span data-stu-id="04be9-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="04be9-135">Składnia atrybutu z jawną właściwością elementu członkowskiego dla ciągu inicjującego.</span><span class="sxs-lookup"><span data-stu-id="04be9-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="04be9-136">W implementacji usług języka XAML platformy .NET obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.StaticExtension> klasę.</span><span class="sxs-lookup"><span data-stu-id="04be9-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="04be9-137">`x:Static` jest rozszerzeniem znaczników.</span><span class="sxs-lookup"><span data-stu-id="04be9-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="04be9-138">Wszystkie rozszerzenia znaczników w języku XAML używają `{` `}` znaków i w ich składni atrybutów, która jest konwencją, za pomocą której procesor XAML rozpoznaje, że rozszerzenie znacznika musi zawierać wartość.</span><span class="sxs-lookup"><span data-stu-id="04be9-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="04be9-139">Aby uzyskać więcej informacji na temat rozszerzeń znaczników, zobacz [znaczniki rozszerzeń dla języka XAML — Omówienie](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="04be9-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="04be9-140">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="04be9-140">WPF Usage Notes</span></span>

<span data-ttu-id="04be9-141">Domyślna przestrzeń nazw języka XAML, która jest używana w programowaniu WPF, nie zawiera wielu użytecznych właściwości statycznych i większość przydatnych właściwości statycznych obsługuje takie jak konwertery typów, które ułatwiają użycie bez konieczności `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="04be9-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="04be9-142">W przypadku właściwości statycznych należy zmapować prefiks dla przestrzeni nazw XAML, jeśli jest spełniony jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="04be9-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="04be9-143">Odwołujesz się do typu, który istnieje w WPF, ale nie jest częścią domyślnej przestrzeni nazw XAML dla WPF ( `http://schemas.microsoft.com/winfx/2006/xaml/presentation` ).</span><span class="sxs-lookup"><span data-stu-id="04be9-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="04be9-144">Jest to dość typowy scenariusz użycia programu `x:Static` .</span><span class="sxs-lookup"><span data-stu-id="04be9-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="04be9-145">Na przykład można użyć `x:Static` odwołania z mapowaniem przestrzeni nazw XAML do <xref:System> przestrzeni nazw CLR i zestawu Mscorlib, aby odwołać się do właściwości statycznych <xref:System.Environment> klasy.</span><span class="sxs-lookup"><span data-stu-id="04be9-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="04be9-146">Odwołujesz się do typu z niestandardowego zestawu.</span><span class="sxs-lookup"><span data-stu-id="04be9-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="04be9-147">Odwołujesz się do typu, który istnieje w zestawie WPF, ale ten typ znajduje się w przestrzeni nazw CLR, która nie została zmapowana do domyślnej przestrzeni nazw języka XAML WPF.</span><span class="sxs-lookup"><span data-stu-id="04be9-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="04be9-148">Mapowanie przestrzeni nazw CLR do domyślnej przestrzeni nazw XAML dla WPF jest wykonywane przez definicje w różnych zestawach WPF (Aby uzyskać więcej informacji na temat tego pojęcia, zobacz [przestrzenie nazw XAML i mapowanie przestrzeni nazw dla WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)).</span><span class="sxs-lookup"><span data-stu-id="04be9-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)).</span></span> <span data-ttu-id="04be9-149">Niemapowane przestrzenie nazw środowiska CLR mogą istnieć, jeśli przestrzeń nazw środowiska CLR składa się głównie z definicji klas, które nie są zwykle przeznaczone dla języka XAML, takich jak <xref:System.Windows.Threading> .</span><span class="sxs-lookup"><span data-stu-id="04be9-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="04be9-150">Aby uzyskać więcej informacji na temat używania prefiksów i przestrzeni nazw XAML dla WPF, zobacz [przestrzenie nazw XAML i mapowanie przestrzeni nazw dla języka XAML WPF](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="04be9-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).</span></span>

## <a name="see-also"></a><span data-ttu-id="04be9-151">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="04be9-151">See also</span></span>

- [<span data-ttu-id="04be9-152">x:Type — Rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="04be9-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="04be9-153">Typy migrowane z WPF do System.Xaml</span><span class="sxs-lookup"><span data-stu-id="04be9-153">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
