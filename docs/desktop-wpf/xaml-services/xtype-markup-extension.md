---
title: x:Type — Rozszerzenie znaczników
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: 00e6684f6ad1eb8d96f72f49bd5e0d211c8166c3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559073"
---
# <a name="xtype-markup-extension"></a>x:Type — Rozszerzenie znaczników

Dostarcza obiekt CLR <xref:System.Type> , który jest typem podstawowym dla określonego typu XAML.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`prefix`|Opcjonalny. Prefiks, który mapuje niedomyślną przestrzeń nazw XAML. Określanie prefiksu jest często niepotrzebne. Zobacz uwagi.|
|`typeNameValue`|Wymagany. Nazwa typu rozpoznawana jako bieżąca domyślna przestrzeń nazw XAML; lub określony zamapowany prefiks, jeśli `prefix` został podany.|

## <a name="remarks"></a>Uwagi

`x:Type`Rozszerzenie znaczników ma podobną funkcję do `typeof()` operatora w języku C# lub `GetType` operator w programie Microsoft Visual Basic.

`x:Type`Rozszerzenie znaczników dostarcza zachowanie konwersji od-String dla właściwości, które mają typ <xref:System.Type> . Dane wejściowe są typu XAML. Relacja między wejściowym typem XAML i wyjściowym środowiskiem CLR <xref:System.Type> polega na tym, że dane wyjściowe <xref:System.Type> są <xref:System.Xaml.XamlType.UnderlyingType%2A> danymi wejściowymi <xref:System.Xaml.XamlType> , po wyszukaniu niezbędnych informacji <xref:System.Xaml.XamlType> opartych na kontekście schematu XAML i <xref:System.Windows.Markup.IXamlTypeResolver> usłudze udostępnianej przez kontekst.

W usługach programu .NET XAML obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.TypeExtension> klasę.

W określonych implementacjach platformy niektóre właściwości, które przyjmuje <xref:System.Type> jako wartość, mogą akceptować nazwę typu bezpośrednio (wartość ciągu typu `Name` ). Jednak wdrożenie tego zachowania jest złożonym scenariuszem. Aby zapoznać się z przykładami, zobacz sekcję "uwagi dotyczące użycia platformy WPF" poniżej.

Składnią atrybutu jest składnia najczęściej używana z tym rozszerzeniem znacznika. Token ciągu podany po `x:Type` ciągu identyfikatora jest przypisywany jako <xref:System.Windows.Markup.TypeExtension.TypeName%2A> wartość źródłowej <xref:System.Windows.Markup.TypeExtension> klasy rozszerzenia. W obszarze domyślnego kontekstu schematu XAML dla usług .NET XAML, który jest oparty na typach CLR, wartość tego atrybutu jest <xref:System.Reflection.MemberInfo.Name%2A> żądanym typem lub zawiera, <xref:System.Reflection.MemberInfo.Name%2A> poprzedzony prefiksem dla mapowania przestrzeni nazw języka XAML innego niż domyślne.

`x:Type`Rozszerzenie znaczników może być używane w składni elementu obiektu. W takim przypadku określenie wartości <xref:System.Windows.Markup.TypeExtension.TypeName%2A> właściwości jest wymagane do prawidłowego zainicjowania rozszerzenia.

`x:Type`Rozszerzenia znaczników można także użyć jako atrybutu pełnego, jednak to użycie nie jest typowe:`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF

### <a name="default-xaml-namespace-and-type-mapping"></a>Domyślna przestrzeń nazw XAML i mapowanie typu

Domyślna przestrzeń nazw XAML dla programowania WPF zawiera większość typów XAML potrzebnych dla typowych scenariuszy języka XAML; w związku z tym, można często unikać prefiksów podczas odwoływania się do wartości typu XAML. Może być konieczne zamapowanie prefiksu, jeśli odwołujesz się do typu z niestandardowego zestawu lub dla typów, które istnieją w zestawie WPF, ale pochodzą z przestrzeni nazw CLR, która nie została zmapowana do domyślnej przestrzeni nazw XAML. Aby uzyskać więcej informacji na temat prefiksów, przestrzeni nazw XAML i mapowania przestrzeni nazw środowiska CLR, zobacz [przestrzenie nazw XAML i mapowanie przestrzeni nazw dla języka XAML WPF](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).

### <a name="type-properties-that-support-typename-as-string"></a>Właściwości typu, które obsługują atrybut TypeName as

WPF obsługuje techniki, które umożliwiają określanie wartości niektórych właściwości typu <xref:System.Type> bez konieczności `x:Type` używania rozszerzenia znaczników. Zamiast tego można określić wartość jako ciąg, który określa nazwę typu. Przykłady to <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> i <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> . Obsługa tego zachowania nie jest zapewniana za pomocą konwerterów typów ani rozszerzeń znaczników. Zamiast tego jest to zachowanie odroczenia zaimplementowane za pomocą <xref:System.Windows.FrameworkElementFactory> .

Program Silverlight obsługuje podobną Konwencję. W rzeczywistości Technologia Silverlight obecnie nie obsługuje obsługi `{x:Type}` języka XAML i nie akceptuje `{x:Type}` użycia poza kilka okoliczności, które są przeznaczone do obsługi migracji języka XAML w technologii WPF. W związku z tym zachowanie typu TypeName jest wbudowane we wszystkich obliczeniach właściwości natywnych Silverlight, gdzie a <xref:System.Type> jest wartością.

## <a name="xaml-2009"></a>XAML 2009

Język XAML 2009 zapewnia dodatkową pomoc techniczną dla typów ogólnych i modyfikuje zachowanie funkcji programu `x:TypeArguments` i, `x:Type` Aby zapewnić tę pomoc techniczną.

- `x:TypeArguments` i skojarzony element obiektu dla tworzenia wystąpienia obiektu ogólnego może znajdować się w elementach innych niż główny. Aby uzyskać więcej informacji, zobacz sekcję "XAML 2009" w [dyrektywie x:TypeArguments —](xtypearguments-directive.md).

- XAML 2009 obsługuje składnię do określania ograniczenia typu ogólnego w znaczniku. Może to być używane przez, `x:TypeArguments` przez `x:Type` lub przez dwie funkcje w połączeniu.

- Implementacja języka XAML WPF podczas przetwarzania kodu XAML 2009 do załadowania dodaje również tę możliwość do zachowania niejawnej konwersji typów dla niektórych właściwości platformy, które używają typu <xref:System.Type> .

W programie WPF można używać funkcji języka XAML 2009, ale tylko w przypadku swobodnego języka XAML (XAML, który nie jest skompilowany do adiustacji). Skompilowane znaczniki XAML dla WPF i forma BAML języka XAML nie obsługują obecnie słów kluczowych i funkcji języka XAML 2009.

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.Style>
- [Tworzenie szablonów i stylów](../fundamentals/styles-templates-overview.md)
- [Omówienie XAML (WPF)](../fundamentals/xaml.md)
- [Rozszerzenia znacznikowania i WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
