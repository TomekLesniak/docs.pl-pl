---
title: x:FieldModifier — dyrektywa
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 4e67a6dac49b8d6a7d316526f99a1519b08fd68b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554478"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier — dyrektywa
Modyfikuje zachowanie kompilacji XAML, aby pola dla odwołań do nazwanych obiektów były zdefiniowane z <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> dostępem zamiast <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> zachowania domyślnego.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|*Publiczne*|Dokładny ciąg, który można określić w zależności od <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> używanego języka programowania związanego z kodem. Zobacz uwagi.|

## <a name="dependencies"></a>Zależności

 Jeśli produkcja XAML używa `x:FieldModifier` dowolnego miejsca, element główny tej produkcji XAML musi deklarować [dyrektywę x:Class](xclass-directive.md).

## <a name="remarks"></a>Uwagi

`x:FieldModifier` nie ma znaczenia w przypadku deklarowania ogólnego poziomu dostępu klasy lub jej elementów członkowskich. Jest to istotne tylko w przypadku przetwarzania kodu XAML, gdy określony obiekt XAML będący częścią produkcji XAML jest przetwarzany i stanie się obiektem, który jest potencjalnie dostępny na grafie obiektów aplikacji. Domyślnie odwołanie do pola dla takiego obiektu jest przechowywane jako prywatne, co uniemożliwia konsumentom kontroli bezpośrednie modyfikowanie grafu obiektów. Zamiast tego użytkownicy kontroli powinni zmodyfikować Graf obiektów przy użyciu standardowych wzorców włączonych przez modele programowania, takich jak Uzyskiwanie głównego układu, kolekcje elementów podrzędnych, dedykowane właściwości publiczne itd.

Wartość `x:FieldModifier` atrybutu różni się w zależności od języka programowania, a jego cel może się różnić w określonych strukturach. Ciąg, który ma być używany, zależy od tego, w jaki sposób każdy język implementuje swój <xref:System.CodeDom.Compiler.CodeDomProvider> i konwertery typów, które zwraca, aby zdefiniować znaczenie dla <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> i <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , oraz czy w tym języku jest uwzględniana wielkość liter.

- Dla języka C# ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` .

- W przypadku programu Microsoft Visual Basic .NET ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public` .

- W przypadku języka C++/CLI nie istnieją żadne elementy docelowe dla języka XAML. w związku z tym ciąg do przekazania jest niezdefiniowany.

Można również określić <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( `internal` w języku C#, `Friend` w Visual Basic), ale określanie <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> jest nietypowe, ponieważ `NotPublic` zachowanie jest już domyślne.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> jest zachowaniem domyślnym, ponieważ jest rzadko, gdy kod poza zestawem, który skompilowany XAML, potrzebuje dostępu do elementu utworzonego w języku XAML. Architektura zabezpieczeń WPF wraz z zachowaniem kompilacji XAML nie deklaruje pól, które przechowują wystąpienia elementów jako publiczne, chyba że określono opcję `x:FieldModifier` zezwalania na dostęp publiczny.

`x:FieldModifier` ma zastosowanie tylko do elementów z [dyrektywą x:Name](xname-directive.md) , ponieważ ta nazwa jest używana do odwoływania się do pola po jego publicznym.

Domyślnie Klasa częściowa elementu głównego jest publiczna; można jednak sprawić, aby był niepubliczny za pomocą [dyrektywy x:ClassModifier —](xclassmodifier-directive.md). [Dyrektywa x:ClassModifier —](xclassmodifier-directive.md) ma także wpływ na poziom dostępu wystąpienia klasy elementu głównego. Można umieścić zarówno `x:Name` element, jak i `x:FieldModifier` na elemencie głównym, ale tylko publiczną kopię pola elementu głównego z prawdziwym poziomem dostępu klasy elementu głównego, nadal kontrolowanym przez [dyrektywę x:ClassModifier —](xclassmodifier-directive.md).

## <a name="see-also"></a>Zobacz także

- [Klasy XAML i niestandardowe dla WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [Związane z kodem i XAML w WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:Name — dyrektywa](xname-directive.md)
- [Kompilowanie aplikacji WPF (WPF)](/dotnet/desktop/wpf/app-development/building-a-wpf-application-wpf)
- [x:ClassModifier — dyrektywa](xclassmodifier-directive.md)
