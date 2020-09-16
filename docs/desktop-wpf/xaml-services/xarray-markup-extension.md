---
title: x:Array — Rozszerzenie znaczników
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555175"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="a5a11-102">x:Array — Rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="a5a11-102">x:Array Markup Extension</span></span>

<span data-ttu-id="a5a11-103">Zapewnia ogólną pomoc techniczną dla tablic obiektów w języku XAML za pomocą rozszerzenia znaczników.</span><span class="sxs-lookup"><span data-stu-id="a5a11-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="a5a11-104">Odnosi się to do `x:ArrayExtension` typu XAML w [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="a5a11-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a5a11-105">Użycie elementu obiektu języka XAML</span><span class="sxs-lookup"><span data-stu-id="a5a11-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="a5a11-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="a5a11-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="a5a11-107">Nazwa typu, który `x:Array` będzie zawierać.</span><span class="sxs-lookup"><span data-stu-id="a5a11-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="a5a11-108">`typeName` może być (i często) prefiksem przestrzeni nazw XAML, która zawiera definicje typów XAML.</span><span class="sxs-lookup"><span data-stu-id="a5a11-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="a5a11-109">Zawartość elementów, która jest przypisana do `ArrayExtension.Items` Właściwości wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="a5a11-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="a5a11-110">Zazwyczaj te elementy są określone jako jeden lub więcej elementów obiektów zawartych w `x:Array` tagach otwierających i zamykających.</span><span class="sxs-lookup"><span data-stu-id="a5a11-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="a5a11-111">Obiektów określonych tutaj można przypisać do typu XAML określonego w `typeName` .</span><span class="sxs-lookup"><span data-stu-id="a5a11-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5a11-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a5a11-112">Remarks</span></span>

<span data-ttu-id="a5a11-113">`Type` jest wymaganym atrybutem dla wszystkich `x:Array` elementów obiektu.</span><span class="sxs-lookup"><span data-stu-id="a5a11-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="a5a11-114">`Type`Wartość parametru nie musi używać `x:Type` rozszerzenia znaczników; krótka nazwa typu jest typem XAML, który można określić jako ciąg.</span><span class="sxs-lookup"><span data-stu-id="a5a11-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="a5a11-115">W implementacji usług języka XAML platformy .NET relacja między wejściowym typem XAML i wyjściowym środowiskiem CLR dla <xref:System.Type> utworzonej tablicy ma wpływ na kontekst usługi dla rozszerzeń znaczników.</span><span class="sxs-lookup"><span data-stu-id="a5a11-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="a5a11-116">Dane wyjściowe <xref:System.Type> są <xref:System.Xaml.XamlType.UnderlyingType%2A> typu danych wejściowych XAML, po wyszukaniu niezbędnego <xref:System.Xaml.XamlType> kontekstu schematu XAML i <xref:System.Windows.Markup.IXamlTypeResolver> usługi udostępnianej przez kontekst.</span><span class="sxs-lookup"><span data-stu-id="a5a11-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="a5a11-117">Podczas przetwarzania zawartość tablicy jest przypisywana do `ArrayExtension.Items` Właściwości wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="a5a11-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="a5a11-118">W <xref:System.Windows.Markup.ArrayExtension> implementacji jest to reprezentowane przez <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a5a11-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a5a11-119">W implementacji usług języka XAML platformy .NET obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.ArrayExtension> klasę.</span><span class="sxs-lookup"><span data-stu-id="a5a11-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="a5a11-120"><xref:System.Windows.Markup.ArrayExtension> nie jest zapieczętowany i może służyć jako podstawa implementacji rozszerzenia znacznika dla niestandardowego typu tablicy.</span><span class="sxs-lookup"><span data-stu-id="a5a11-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="a5a11-121">`x:Array` jest bardziej przeznaczony do ogólnego rozszerzania języków w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="a5a11-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="a5a11-122">Ale `x:Array` mogą również być przydatne do określania wartości XAML niektórych właściwości, które pobierają kolekcje obsługiwane przez język XAML jako ich zawartość właściwości strukturalnej.</span><span class="sxs-lookup"><span data-stu-id="a5a11-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="a5a11-123">Na przykład można określić zawartość <xref:System.Collections.IEnumerable> właściwości przy użyciu `x:Array` .</span><span class="sxs-lookup"><span data-stu-id="a5a11-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="a5a11-124">`x:Array` jest rozszerzeniem znaczników.</span><span class="sxs-lookup"><span data-stu-id="a5a11-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="a5a11-125">Rozszerzenia znaczników są zazwyczaj implementowane w sytuacji, gdy istnieje wymóg, aby wartości atrybutów były wyprowadzane w postaci innej niż wartości literałów lub nazwy programów obsługi, a wymóg ma charakter bardziej globalny niż zwykłe umieszczenie konwerterów typów w niektórych typach lub właściwościach.</span><span class="sxs-lookup"><span data-stu-id="a5a11-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="a5a11-126">`x:Array` jest częściowo wyjątkiem od tej reguły, ponieważ zamiast udostępniać alternatywną obsługę wartości atrybutów, `x:Array` zapewnia alternatywną obsługę swojej wewnętrznej zawartości tekstowej.</span><span class="sxs-lookup"><span data-stu-id="a5a11-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="a5a11-127">Takie zachowanie włącza typy, które mogą nie być obsługiwane przez istniejący model zawartości, aby można je było grupować w tablicę i przywoływane później w kodzie przez uzyskanie dostępu do nazwanej tablicy; Możesz wywoływać <xref:System.Array> metody, aby pobrać pojedyncze elementy tablicy.</span><span class="sxs-lookup"><span data-stu-id="a5a11-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="a5a11-128">Wszystkie rozszerzenia znaczników w języku XAML używają nawiasów klamrowych ( {,} `)` w składni atrybutu, która jest konwencją, za pomocą której procesor XAML rozpoznaje, że rozszerzenie znacznika musi przetwarzać wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a5a11-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="a5a11-129">Aby uzyskać więcej informacji na temat ogólnych rozszerzeń znaczników, zobacz [Typy konwerterów i rozszerzenia znaczników dla języka XAML](type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="a5a11-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="a5a11-130">W języku XAML 2009, `x:Array` jest zdefiniowany jako pierwotny język zamiast rozszerzenia znacznika.</span><span class="sxs-lookup"><span data-stu-id="a5a11-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="a5a11-131">Aby uzyskać więcej informacji, zobacz [typy wbudowane dla wspólnych elementów podstawowych języka XAML](types-for-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="a5a11-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a5a11-132">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="a5a11-132">WPF Usage Notes</span></span>

<span data-ttu-id="a5a11-133">Zazwyczaj elementy obiektu, które wypełniają `x:Array` nie są elementami, które znajdują się w [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] przestrzeni nazw XAML, i wymagają mapowania prefiksu do przestrzeni nazw języka XAML innego niż domyślna.</span><span class="sxs-lookup"><span data-stu-id="a5a11-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="a5a11-134">Na przykład, poniżej znajduje się prosta tablica dwóch ciągów, z `sys` prefiksem (i również `x` ) zdefiniowanym na poziomie tablicy.</span><span class="sxs-lookup"><span data-stu-id="a5a11-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="a5a11-135">W przypadku typów niestandardowych, które są używane jako elementy tablicy, Klasa musi również obsługiwać wymagania dotyczące wystąpienia w kodzie XAML jako elementy obiektu.</span><span class="sxs-lookup"><span data-stu-id="a5a11-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="a5a11-136">Aby uzyskać więcej informacji, zobacz [XAML i klasy niestandardowe dla WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span><span class="sxs-lookup"><span data-stu-id="a5a11-136">For more information, see [XAML and Custom Classes for WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5a11-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a5a11-137">See also</span></span>

- [<span data-ttu-id="a5a11-138">Rozszerzenia znacznikowania i WPF XAML</span><span class="sxs-lookup"><span data-stu-id="a5a11-138">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [<span data-ttu-id="a5a11-139">Typy migrowane z WPF do System.Xaml</span><span class="sxs-lookup"><span data-stu-id="a5a11-139">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
