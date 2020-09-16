---
title: x:ClassModifier — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544820"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier — dyrektywa
Modyfikuje zachowanie kompilacji XAML, gdy `x:Class` jest również udostępniane. W odróżnieniu od tworzenia części, `class` która ma `Public` poziom dostępu (wartość domyślna), podano wartość `x:Class` z `NotPublic` poziomu dostępu. To zachowanie ma wpływ na poziom dostępu dla klasy w wygenerowanych zestawach.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|*NotPublic*|Dokładny ciąg, który ma zostać przekazany do określonych <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> wartości, w zależności od języka programowania związanego z kodem, który jest używany. Zobacz uwagi.|

## <a name="dependencies"></a>Zależności

[x:Class](xclass-directive.md) musi również znajdować się na tym samym elemencie, a element musi być elementem głównym na stronie. Aby uzyskać więcej informacji, zobacz [ \[ sekcję MS-XAML \] 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Uwagi

Wartość `x:ClassModifier` w polu Użycie usług .NET XAML jest różna w zależności od języka programowania. Ciąg, który ma być używany, zależy od tego, w jaki sposób każdy język implementuje swój <xref:System.CodeDom.Compiler.CodeDomProvider> i konwertery typów, które zwraca, aby zdefiniować znaczenie dla <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> i <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , oraz czy w tym języku jest uwzględniana wielkość liter.

- Dla języka C# ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal` .

- W przypadku programu Microsoft Visual Basic .NET ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend` .

- W przypadku języka C++/CLI nie istnieją żadne elementy docelowe, które obsługują kompilowanie kodu XAML; w związku z tym wartość do przekazania nie została określona.

Można również określić <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` w języku C#, `Public` w Visual Basic), jednak Określanie <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> jest nierzadko wykonywane, ponieważ <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> jest już zachowaniem domyślnym.

Inne wartości mające równoważne ograniczenia poziomu dostępu do kodu użytkownika, takie jak `private` w języku C#, nie są istotne dla `x:ClassModifier` ponieważ zagnieżdżone odwołania do klas nie są obsługiwane w języku XAML i w związku z tym <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modyfikator ma ten sam efekt.

## <a name="security-notes"></a>Uwagi dotyczące zabezpieczeń

Poziom dostępu zadeklarowany w programie `x:ClassModifier` jest nadal objęty interpretacją przez poszczególne struktury i ich możliwości. WPF obejmuje możliwości ładowania i tworzenia wystąpienia typów `x:ClassModifier` , gdzie is `internal` , jeśli ta klasa jest przywoływana z zasobu WPF za pośrednictwem odwołania do identyfikatora URI pakietu. W związku z tym w tym przypadku i potencjalnie innym, podobnym do wdrożonym przez inne struktury, nie należy polegać wyłącznie na tym, `x:ClassModifier` Aby zablokować wszystkie możliwe próby utworzenia wystąpienia.

## <a name="see-also"></a>Zobacz także

- [x:Class — dyrektywa](xclass-directive.md)
- [Związane z kodem i XAML w WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:FieldModifier — dyrektywa](xfieldmodifier-directive.md)
- [Zabezpieczenia (WPF)](/dotnet/desktop/wpf/security-wpf)
- [Typy migrowane z WPF do System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
