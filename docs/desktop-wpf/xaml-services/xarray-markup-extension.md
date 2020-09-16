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
# <a name="xarray-markup-extension"></a>x:Array — Rozszerzenie znaczników

Zapewnia ogólną pomoc techniczną dla tablic obiektów w języku XAML za pomocą rozszerzenia znaczników. Odnosi się to do `x:ArrayExtension` typu XAML w [MS-XAML].

## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`typeName`|Nazwa typu, który `x:Array` będzie zawierać. `typeName` może być (i często) prefiksem przestrzeni nazw XAML, która zawiera definicje typów XAML.|
|`arrayContents`|Zawartość elementów, która jest przypisana do `ArrayExtension.Items` Właściwości wewnętrznej. Zazwyczaj te elementy są określone jako jeden lub więcej elementów obiektów zawartych w `x:Array` tagach otwierających i zamykających. Obiektów określonych tutaj można przypisać do typu XAML określonego w `typeName` .|

## <a name="remarks"></a>Uwagi

`Type` jest wymaganym atrybutem dla wszystkich `x:Array` elementów obiektu. `Type`Wartość parametru nie musi używać `x:Type` rozszerzenia znaczników; krótka nazwa typu jest typem XAML, który można określić jako ciąg.

W implementacji usług języka XAML platformy .NET relacja między wejściowym typem XAML i wyjściowym środowiskiem CLR dla <xref:System.Type> utworzonej tablicy ma wpływ na kontekst usługi dla rozszerzeń znaczników. Dane wyjściowe <xref:System.Type> są <xref:System.Xaml.XamlType.UnderlyingType%2A> typu danych wejściowych XAML, po wyszukaniu niezbędnego <xref:System.Xaml.XamlType> kontekstu schematu XAML i <xref:System.Windows.Markup.IXamlTypeResolver> usługi udostępnianej przez kontekst.

Podczas przetwarzania zawartość tablicy jest przypisywana do `ArrayExtension.Items` Właściwości wewnętrznej. W <xref:System.Windows.Markup.ArrayExtension> implementacji jest to reprezentowane przez <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .

W implementacji usług języka XAML platformy .NET obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.ArrayExtension> klasę. <xref:System.Windows.Markup.ArrayExtension> nie jest zapieczętowany i może służyć jako podstawa implementacji rozszerzenia znacznika dla niestandardowego typu tablicy.

`x:Array` jest bardziej przeznaczony do ogólnego rozszerzania języków w języku XAML. Ale `x:Array` mogą również być przydatne do określania wartości XAML niektórych właściwości, które pobierają kolekcje obsługiwane przez język XAML jako ich zawartość właściwości strukturalnej. Na przykład można określić zawartość <xref:System.Collections.IEnumerable> właściwości przy użyciu `x:Array` .

`x:Array` jest rozszerzeniem znaczników. Rozszerzenia znaczników są zazwyczaj implementowane w sytuacji, gdy istnieje wymóg, aby wartości atrybutów były wyprowadzane w postaci innej niż wartości literałów lub nazwy programów obsługi, a wymóg ma charakter bardziej globalny niż zwykłe umieszczenie konwerterów typów w niektórych typach lub właściwościach. `x:Array` jest częściowo wyjątkiem od tej reguły, ponieważ zamiast udostępniać alternatywną obsługę wartości atrybutów, `x:Array` zapewnia alternatywną obsługę swojej wewnętrznej zawartości tekstowej. Takie zachowanie włącza typy, które mogą nie być obsługiwane przez istniejący model zawartości, aby można je było grupować w tablicę i przywoływane później w kodzie przez uzyskanie dostępu do nazwanej tablicy; Możesz wywoływać <xref:System.Array> metody, aby pobrać pojedyncze elementy tablicy.

Wszystkie rozszerzenia znaczników w języku XAML używają nawiasów klamrowych ( {,} `)` w składni atrybutu, która jest konwencją, za pomocą której procesor XAML rozpoznaje, że rozszerzenie znacznika musi przetwarzać wartość atrybutu. Aby uzyskać więcej informacji na temat ogólnych rozszerzeń znaczników, zobacz [Typy konwerterów i rozszerzenia znaczników dla języka XAML](type-converters-and-markup-extensions.md).

W języku XAML 2009, `x:Array` jest zdefiniowany jako pierwotny język zamiast rozszerzenia znacznika. Aby uzyskać więcej informacji, zobacz [typy wbudowane dla wspólnych elementów podstawowych języka XAML](types-for-primitives.md).

## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF

Zazwyczaj elementy obiektu, które wypełniają `x:Array` nie są elementami, które znajdują się w [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] przestrzeni nazw XAML, i wymagają mapowania prefiksu do przestrzeni nazw języka XAML innego niż domyślna.

Na przykład, poniżej znajduje się prosta tablica dwóch ciągów, z `sys` prefiksem (i również `x` ) zdefiniowanym na poziomie tablicy.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

W przypadku typów niestandardowych, które są używane jako elementy tablicy, Klasa musi również obsługiwać wymagania dotyczące wystąpienia w kodzie XAML jako elementy obiektu. Aby uzyskać więcej informacji, zobacz [XAML i klasy niestandardowe dla WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).

## <a name="see-also"></a>Zobacz także

- [Rozszerzenia znacznikowania i WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [Typy migrowane z WPF do System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
