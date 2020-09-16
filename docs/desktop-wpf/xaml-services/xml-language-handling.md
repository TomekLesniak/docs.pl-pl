---
title: xml:lang — Obsługa w XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 92d1eda62ff394df54d9607bab46d9950681e603
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548211"
---
# <a name="xmllang-handling-in-xaml"></a>xml:lang — Obsługa w XAML

Ten `xml:lang` atrybut jest atrybutem zdefiniowanym przez XML, który deklaruje informacje o języku i kulturze dla elementu w formacie XML. Takie samo znaczenie atrybutu utrzymuje się w języku XAML; Niektóre dodatkowe zagadnienia są jednak stosowane.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|*rfc3066lang*|Ciąg pochodzący ze standardu [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) i identyfikujący język lub region języka. Gdy jest to ostatni, język i region są rozdzielone pojedynczym łącznikiem. <xref:System.Windows.Markup.XmlLanguage>Aby uzyskać więcej informacji na temat wartości i formatu, zobacz.|

## <a name="remarks"></a>Uwagi

Definicja `xml:lang` atrybutu w programie [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] jest pochodną, `xml:lang` jak zdefiniowano jako "Special attribute" przez organizacja World Wide Web Consortium (W3C) dla XML. Informacje o języku i kulturze mogą być przetwarzane na różne sposoby według elementów, w zależności od ich implementacji; nie ma jednak domyślnego [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] przetwarzania `xml:lang` atrybutu.

Wartość domyślna `xml:lang` atrybutu jest ciągiem pustym na poziomie atrybutu.

`xml:lang`Efekty atrybutu i wartość atrybutu są zwykle perpetuated do elementów podrzędnych, gdy są interpretowane przez systemy, które działają na `xml:lang` wartościach.

W przypadku interpretacji przez autorów XAML usług .NET XAML, `xml:lang` wartość może utworzyć <xref:System.Windows.Markup.XmlLanguage> lub <xref:System.Globalization.CultureInfo> obiekty w reprezentacji bazowego obiektu, jednak to zachowanie zależy od tego, czy wartość określona dla `xml:lang` jest prawidłową konstrukcją dla tych klas.

Struktury programu mogą tworzyć skojarzenia między właściwościami zdefiniowanymi przez platformę i znaczenie `xml:lang` w kodzie XML przez zastosowanie <xref:System.Windows.Markup.XmlLangPropertyAttribute> do właściwości.

## <a name="wpf-usage-nodes"></a>Węzły użycia WPF

Dla elementów, które są klasami pochodnymi <xref:System.Windows.FrameworkElement> lub <xref:System.Windows.FrameworkContentElement> , można użyć równoważnej <xref:System.Windows.FrameworkElement.Language%2A> właściwości zależności zamiast `xml:lang` atrybutu. Domyślnie <xref:System.Windows.FrameworkElement.Language%2A> Właściwość używa wartości "pl-US", jeśli nie została ustawiona inaczej, przez właściwość lub poprzez przetwarzanie `xml:lang` atrybutu.

## <a name="see-also"></a>Zobacz także

- [Globalizacja dla WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
