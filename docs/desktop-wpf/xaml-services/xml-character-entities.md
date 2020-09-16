---
title: Jednostki znaków XML i XAML
ms.date: 03/30/2017
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
ms.openlocfilehash: 1ba99cda512bc5e18c646b09f26672a39c1cf53c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548195"
---
# <a name="xml-character-entities-and-xaml"></a>Jednostki znaków XML i XAML

KOD XAML używa jednostek znaków zdefiniowanych w kodzie XML dla znaków specjalnych. W tym temacie opisano niektóre określone jednostki znakowe i ogólne zagadnienia dotyczące innych koncepcji XML w języku XAML.

## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>Jednostki znakowe i problemy ucieczki, które są unikatowe dla języka XAML

Znaczniki języka XAML zwykle używają tych samych jednostek znaków i sekwencji unikowych, które są zdefiniowane w kodzie XML.

Głównym wyjątkiem jest to, że nawiasy klamrowe ({i}) mają znaczenie w języku XAML, ponieważ te znaki informują procesor XAML, że sekwencja znaków ujęta w nawiasy klamrowe musi być interpretowana jako rozszerzenie znaczników. Aby uzyskać więcej informacji na temat rozszerzeń znaczników, zobacz [znaczniki rozszerzeń dla języka XAML — Omówienie](markup-extensions-overview.md).

Można jednak nadal wyświetlać nawiasy klamrowe jako znaki literału przy użyciu sekwencji unikowej, która jest określona dla języka XAML zamiast XML. Aby uzyskać więcej informacji, zobacz [ {} rozszerzenie sekwencji unikowej](escape-sequence-markup-extension.md).

Należy zauważyć, że ukośnik odwrotny ( \\ ) nie wymaga sekwencji ucieczki, gdy jest obsługiwany jako ciąg.

## <a name="xml-character-entities"></a>Jednostki znaków XML

Jak wspomniano wcześniej, większość jednostek znaków i sekwencji ucieczki, które są zwykle używane do pisania znaczników XAML, są definiowane przez XML. Ten temat nie zawiera pełnej listy tych jednostek; Szczegółowe informacje o jednostkach można znaleźć w dokumentacji zewnętrznej, np. w specyfikacjach XML. Jednak dla wygody w tym temacie wymieniono niektóre z określonych jednostek znaków XML, które są zwykle używane w znacznikach XAML.

|Znak|Jednostka|Uwagi|
|---------------|------------|-----------|
|& (znak)|\&ograniczony|Musi być używany zarówno dla wartości atrybutów, jak i dla zawartości elementu.|
|> (znak większy niż)|\&gt|Musi być użyta dla wartości atrybutu, ale > jest akceptowalny jako zawartość elementu, tak długo, jak < nie poprzedza.|
|< (znak mniejszości)|\&przelew|Musi być używana dla wartości atrybutu, ale nie \< is acceptable as the content of an element as long as > jest zgodna.|
|"(znak cudzysłowu prostego)|\&quot;|Musi być użyta dla wartości atrybutu, ale znak cudzysłowu prostego (") jest akceptowalny jako zawartość elementu. Należy zauważyć, że wartości atrybutów mogą być ujęte w pojedynczy znak cudzysłowu (') lub znak cudzysłowu prostego ("); Każdy znak jest wyświetlany jako pierwszy definiuje załącznik wartości atrybutów, a alternatywny cudzysłów może być użyty jako literał w wartości.|
|"(pojedynczy znak cudzysłowu prostego)|\&"|Musi być użyta dla wartości atrybutu, ale pojedynczy znak cudzysłowu (') jest akceptowalny jako zawartość elementu. Należy zauważyć, że wartości atrybutów mogą być ujęte w pojedynczy znak cudzysłowu (') lub znak cudzysłowu prostego ("); Każdy znak jest wyświetlany jako pierwszy definiuje załącznik wartości atrybutów, a alternatywny cudzysłów może być użyty jako literał w wartości.|
|(numeryczne mapowania znaków)|&#*[Integer]*; lub & # x *[HEX]*;|KOD XAML obsługuje mapowania znaków numerycznych do aktywnego kodowania.|
|(spacja nierozdzielająca)|&\#160; (przy założeniu kodowania UTF-8)|Dla elementów dokumentu przepływu lub elementów, które pobierają tekst, taki jak WPF <xref:System.Windows.Controls.TextBox> , spacje nierozdzielające nie są znormalizowane dla znaczników, nawet dla `xml:space="default"` . (Aby uzyskać więcej informacji, zobacz [Przetwarzanie białych miejsc w języku XAML](white-space-processing.md)).|

## <a name="xml-comment-format"></a>Format komentarza XML

XAML używa formatu komentarza XML: początek komentarza to `<!--` , koniec komentarza, `-->,` a sekwencja `--` nie może wystąpić w komentarzu.

## <a name="xml-processing-instructions"></a>Instrukcje przetwarzania XML

KOD XAML obsługuje instrukcje przetwarzania XML zgodnie ze specyfikacjami XML, które wskazują, że instrukcje muszą być przenoszone przez program. Przetwarzanie XAML w usługach .NET XAML nie korzysta z żadnych instrukcji przetwarzania. Inne istniejące platformy, które używają języka XAML, również nie używają instrukcji przetwarzania z języka XAML.

## <a name="see-also"></a>Zobacz także

- [Omówienie XAML (WPF)](../fundamentals/xaml.md)
- [Rozszerzenia znacznikowania i WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [XamlName — Gramatyka](xamlname-grammar.md)
- [Przetwarzanie spacji w XAML](white-space-processing.md)
