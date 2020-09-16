---
title: x:Null — Rozszerzenie znaczników
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549447"
---
# <a name="xnull-markup-extension"></a>x:Null — Rozszerzenie znaczników

Określa `null` jako wartość dla elementu członkowskiego języka XAML.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Uwagi

Słowo kluczowe dla odwołania o wartości null w języku C# i C++ ma wartość null. Słowo kluczowe Microsoft Visual Basic dla odwołania o wartości null to `Nothing` , ale jest zawsze używane `{x:Null}` jako użycie XAML, niezależnie od kodu związanego z kodem, który jest SKOJARZONY z XAML.

`x:Null`Rozszerzenie znaczników nie ma właściwości settable.

Użycie wartości null jest często kojarzone ze współczynnikiem członkowskim języka XAML dla <xref:System.Nullable%601> wartości CLR.

`x:Null`Rozszerzenie znacznika, takie jak wszystkie rozszerzenia ZNACZNIKÓW XAML, używa nawiasów ( `{,}` ) do ucieczki obsługi wartości atrybutów, aby były inne niż literały lub odwołania do obsługi zdarzeń. Składnia atrybutu jest składnią najczęściej używaną z tym rozszerzeniem znacznika. Składnia elementu obiektu `<x:Null />` jest technicznie możliwa, ale rzadko jest używana, ponieważ `x:Null` rozszerzenie znaczników nie ma parametrów pozycyjnych ani argumentów konstrukcji.

Aby uzyskać informacje na temat rozszerzeń znaczników, zobacz [rozszerzenia znaczników i XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).

W usługach programu .NET XAML obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.NullExtension> klasę.

## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF

Należy pamiętać, że `null` nie musi być początkową wartością ustawienia dla właściwości zależności typu odwołania. Początkowa wartość domyślna może różnić się w zależności od właściwości zależności i może opierać się na metadanych specyficznych dla właściwości. Wiele właściwości zależności nie akceptuje `null` jako wartości, za pomocą znaczników ani kodu ze względu na implementacje wywołania zwrotnego walidacji. Aby uzyskać więcej informacji na temat właściwości zależności, zobacz [Omówienie właściwości zależności](/dotnet/desktop/wpf/advanced/dependency-properties-overview).

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Omówienie XAML (WPF)](../fundamentals/xaml.md)
- [Rozszerzenia znacznikowania i WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
