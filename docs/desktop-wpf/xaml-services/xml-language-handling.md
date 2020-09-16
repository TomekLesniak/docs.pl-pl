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
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="8127e-102">xml:lang — Obsługa w XAML</span><span class="sxs-lookup"><span data-stu-id="8127e-102">xml:lang Handling in XAML</span></span>

<span data-ttu-id="8127e-103">Ten `xml:lang` atrybut jest atrybutem zdefiniowanym przez XML, który deklaruje informacje o języku i kulturze dla elementu w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="8127e-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="8127e-104">Takie samo znaczenie atrybutu utrzymuje się w języku XAML; Niektóre dodatkowe zagadnienia są jednak stosowane.</span><span class="sxs-lookup"><span data-stu-id="8127e-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="8127e-105">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="8127e-105">XAML Attribute Usage</span></span>

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a><span data-ttu-id="8127e-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="8127e-106">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="8127e-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="8127e-107">*rfc3066lang*</span></span>|<span data-ttu-id="8127e-108">Ciąg pochodzący ze standardu [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) i identyfikujący język lub region języka.</span><span class="sxs-lookup"><span data-stu-id="8127e-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="8127e-109">Gdy jest to ostatni, język i region są rozdzielone pojedynczym łącznikiem.</span><span class="sxs-lookup"><span data-stu-id="8127e-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="8127e-110"><xref:System.Windows.Markup.XmlLanguage>Aby uzyskać więcej informacji na temat wartości i formatu, zobacz.</span><span class="sxs-lookup"><span data-stu-id="8127e-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8127e-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8127e-111">Remarks</span></span>

<span data-ttu-id="8127e-112">Definicja `xml:lang` atrybutu w programie [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] jest pochodną, `xml:lang` jak zdefiniowano jako "Special attribute" przez organizacja World Wide Web Consortium (W3C) dla XML.</span><span class="sxs-lookup"><span data-stu-id="8127e-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="8127e-113">Informacje o języku i kulturze mogą być przetwarzane na różne sposoby według elementów, w zależności od ich implementacji; nie ma jednak domyślnego [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] przetwarzania `xml:lang` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8127e-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>

<span data-ttu-id="8127e-114">Wartość domyślna `xml:lang` atrybutu jest ciągiem pustym na poziomie atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8127e-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>

<span data-ttu-id="8127e-115">`xml:lang`Efekty atrybutu i wartość atrybutu są zwykle perpetuated do elementów podrzędnych, gdy są interpretowane przez systemy, które działają na `xml:lang` wartościach.</span><span class="sxs-lookup"><span data-stu-id="8127e-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>

<span data-ttu-id="8127e-116">W przypadku interpretacji przez autorów XAML usług .NET XAML, `xml:lang` wartość może utworzyć <xref:System.Windows.Markup.XmlLanguage> lub <xref:System.Globalization.CultureInfo> obiekty w reprezentacji bazowego obiektu, jednak to zachowanie zależy od tego, czy wartość określona dla `xml:lang` jest prawidłową konstrukcją dla tych klas.</span><span class="sxs-lookup"><span data-stu-id="8127e-116">When interpreted by XAML writers of .NET XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>

<span data-ttu-id="8127e-117">Struktury programu mogą tworzyć skojarzenia między właściwościami zdefiniowanymi przez platformę i znaczenie `xml:lang` w kodzie XML przez zastosowanie <xref:System.Windows.Markup.XmlLangPropertyAttribute> do właściwości.</span><span class="sxs-lookup"><span data-stu-id="8127e-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>

## <a name="wpf-usage-nodes"></a><span data-ttu-id="8127e-118">Węzły użycia WPF</span><span class="sxs-lookup"><span data-stu-id="8127e-118">WPF Usage Nodes</span></span>

<span data-ttu-id="8127e-119">Dla elementów, które są klasami pochodnymi <xref:System.Windows.FrameworkElement> lub <xref:System.Windows.FrameworkContentElement> , można użyć równoważnej <xref:System.Windows.FrameworkElement.Language%2A> właściwości zależności zamiast `xml:lang` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8127e-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="8127e-120">Domyślnie <xref:System.Windows.FrameworkElement.Language%2A> Właściwość używa wartości "pl-US", jeśli nie została ustawiona inaczej, przez właściwość lub poprzez przetwarzanie `xml:lang` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8127e-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="8127e-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8127e-121">See also</span></span>

- [<span data-ttu-id="8127e-122">Globalizacja dla WPF</span><span class="sxs-lookup"><span data-stu-id="8127e-122">Globalization for WPF</span></span>](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
