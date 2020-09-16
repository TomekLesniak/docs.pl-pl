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
# <a name="xclassmodifier-directive"></a><span data-ttu-id="3da04-102">x:ClassModifier — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="3da04-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="3da04-103">Modyfikuje zachowanie kompilacji XAML, gdy `x:Class` jest również udostępniane.</span><span class="sxs-lookup"><span data-stu-id="3da04-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="3da04-104">W odróżnieniu od tworzenia części, `class` która ma `Public` poziom dostępu (wartość domyślna), podano wartość `x:Class` z `NotPublic` poziomu dostępu.</span><span class="sxs-lookup"><span data-stu-id="3da04-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="3da04-105">To zachowanie ma wpływ na poziom dostępu dla klasy w wygenerowanych zestawach.</span><span class="sxs-lookup"><span data-stu-id="3da04-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="3da04-106">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="3da04-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="3da04-107">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="3da04-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="3da04-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="3da04-108">*NotPublic*</span></span>|<span data-ttu-id="3da04-109">Dokładny ciąg, który ma zostać przekazany do określonych <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> wartości, w zależności od języka programowania związanego z kodem, który jest używany.</span><span class="sxs-lookup"><span data-stu-id="3da04-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="3da04-110">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="3da04-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="3da04-111">Zależności</span><span class="sxs-lookup"><span data-stu-id="3da04-111">Dependencies</span></span>

<span data-ttu-id="3da04-112">[x:Class](xclass-directive.md) musi również znajdować się na tym samym elemencie, a element musi być elementem głównym na stronie.</span><span class="sxs-lookup"><span data-stu-id="3da04-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="3da04-113">Aby uzyskać więcej informacji, zobacz [ \[ sekcję MS-XAML \] 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="3da04-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="3da04-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3da04-114">Remarks</span></span>

<span data-ttu-id="3da04-115">Wartość `x:ClassModifier` w polu Użycie usług .NET XAML jest różna w zależności od języka programowania.</span><span class="sxs-lookup"><span data-stu-id="3da04-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="3da04-116">Ciąg, który ma być używany, zależy od tego, w jaki sposób każdy język implementuje swój <xref:System.CodeDom.Compiler.CodeDomProvider> i konwertery typów, które zwraca, aby zdefiniować znaczenie dla <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> i <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , oraz czy w tym języku jest uwzględniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="3da04-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="3da04-117">Dla języka C# ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal` .</span><span class="sxs-lookup"><span data-stu-id="3da04-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="3da04-118">W przypadku programu Microsoft Visual Basic .NET ciąg, który ma zostać przekazany do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend` .</span><span class="sxs-lookup"><span data-stu-id="3da04-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="3da04-119">W przypadku języka C++/CLI nie istnieją żadne elementy docelowe, które obsługują kompilowanie kodu XAML; w związku z tym wartość do przekazania nie została określona.</span><span class="sxs-lookup"><span data-stu-id="3da04-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="3da04-120">Można również określić <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` w języku C#, `Public` w Visual Basic), jednak Określanie <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> jest nierzadko wykonywane, ponieważ <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> jest już zachowaniem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="3da04-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="3da04-121">Inne wartości mające równoważne ograniczenia poziomu dostępu do kodu użytkownika, takie jak `private` w języku C#, nie są istotne dla `x:ClassModifier` ponieważ zagnieżdżone odwołania do klas nie są obsługiwane w języku XAML i w związku z tym <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modyfikator ma ten sam efekt.</span><span class="sxs-lookup"><span data-stu-id="3da04-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="3da04-122">Uwagi dotyczące zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="3da04-122">Security Notes</span></span>

<span data-ttu-id="3da04-123">Poziom dostępu zadeklarowany w programie `x:ClassModifier` jest nadal objęty interpretacją przez poszczególne struktury i ich możliwości.</span><span class="sxs-lookup"><span data-stu-id="3da04-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="3da04-124">WPF obejmuje możliwości ładowania i tworzenia wystąpienia typów `x:ClassModifier` , gdzie is `internal` , jeśli ta klasa jest przywoływana z zasobu WPF za pośrednictwem odwołania do identyfikatora URI pakietu.</span><span class="sxs-lookup"><span data-stu-id="3da04-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="3da04-125">W związku z tym w tym przypadku i potencjalnie innym, podobnym do wdrożonym przez inne struktury, nie należy polegać wyłącznie na tym, `x:ClassModifier` Aby zablokować wszystkie możliwe próby utworzenia wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="3da04-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3da04-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3da04-126">See also</span></span>

- [<span data-ttu-id="3da04-127">x:Class — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="3da04-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="3da04-128">Związane z kodem i XAML w WPF</span><span class="sxs-lookup"><span data-stu-id="3da04-128">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="3da04-129">x:FieldModifier — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="3da04-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="3da04-130">Zabezpieczenia (WPF)</span><span class="sxs-lookup"><span data-stu-id="3da04-130">Security (WPF)</span></span>](/dotnet/desktop/wpf/security-wpf)
- [<span data-ttu-id="3da04-131">Typy migrowane z WPF do System.Xaml</span><span class="sxs-lookup"><span data-stu-id="3da04-131">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
