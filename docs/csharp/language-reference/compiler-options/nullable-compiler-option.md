---
description: -Nullable (opcje kompilatora C#)
title: -Nullable (opcje kompilatora C#)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099227"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="344ec-103">-Nullable (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="344ec-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="344ec-104">Opcja **-nullable** pozwala określić kontekst dopuszczający wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="344ec-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="344ec-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="344ec-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="344ec-106">Arguments</span></span>

<span data-ttu-id="344ec-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="344ec-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="344ec-108">Określenie `+` , lub **-nullable**, powoduje, że kompilator włącza kontekst dopuszczający wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="344ec-109">Określenie `-` , która obowiązuje, jeśli nie określono **wartości null**, wyłącza kontekst dopuszczający wartości null.</span><span class="sxs-lookup"><span data-stu-id="344ec-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="344ec-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="344ec-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="344ec-111">Określa opcję kontekstową dopuszczającą wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-111">Specifies the nullable context option.</span></span> <span data-ttu-id="344ec-112">Podobnie jak w przypadku programu `+` lub `-` , aby włączyć i wyłączyć, ale pozwala na zwiększenie stopnia szczegółowości dla specyficznych dla kontekstu wartości null.</span><span class="sxs-lookup"><span data-stu-id="344ec-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="344ec-113">`enable`Argument, który działa tak samo jak w przypadku określenia **wartości null**, włącza kontekst dopuszczający wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="344ec-114">Określenie `disable` spowoduje wyłączenie kontekstu dopuszczającego wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="344ec-115">Gdy podajesz `warnings` argument, **-nullable:** Warnings, jest włączony kontekst ostrzeżenia dopuszczający wartość null.</span><span class="sxs-lookup"><span data-stu-id="344ec-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="344ec-116">Podczas określania `annotations` argumentu **-nullable: adnotacje** kontekst adnotacji z dopuszczaniem wartości null jest włączony.</span><span class="sxs-lookup"><span data-stu-id="344ec-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="344ec-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="344ec-117">Remarks</span></span>

<span data-ttu-id="344ec-118">Analiza przepływu służy do wywnioskowania wartości null zmiennych w kodzie wykonywalnym.</span><span class="sxs-lookup"><span data-stu-id="344ec-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="344ec-119">Wywnioskowana wartość null zmiennej jest niezależna od zadeklarowanej wartości null zmiennej.</span><span class="sxs-lookup"><span data-stu-id="344ec-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="344ec-120">Wywołania metod są analizowane nawet wtedy, gdy są warunkowo pominięte.</span><span class="sxs-lookup"><span data-stu-id="344ec-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="344ec-121">Na przykład <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> w trybie wydania.</span><span class="sxs-lookup"><span data-stu-id="344ec-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="344ec-122">Wywołanie metod o następujących atrybutach będzie miało wpływ na analizę przepływu:</span><span class="sxs-lookup"><span data-stu-id="344ec-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="344ec-123">Proste warunki wstępne: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> i <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="344ec-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="344ec-124">Proste warunki Post: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> i <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="344ec-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="344ec-125">Warunkowe warunki końcowe: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> i <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="344ec-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="344ec-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (na przykład `DoesNotReturnIf(false)` dla <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ) i <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="344ec-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="344ec-127">Warunki końcowe elementu członkowskiego: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> i <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="344ec-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="344ec-128">Globalny kontekst dopuszczający wartość null nie ma zastosowania do wygenerowanych plików kodu.</span><span class="sxs-lookup"><span data-stu-id="344ec-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="344ec-129">Niezależnie od tego ustawienia kontekst dopuszczający wartość null jest *wyłączany* dla każdego pliku źródłowego oznaczonego jako wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="344ec-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="344ec-130">Istnieją cztery sposoby, aby plik został oznaczony jako wygenerowany:</span><span class="sxs-lookup"><span data-stu-id="344ec-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="344ec-131">W pliku. editorconfig Określ `generated_code = true` w sekcji, która odnosi się do tego plik.</span><span class="sxs-lookup"><span data-stu-id="344ec-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="344ec-132">Umieść `<auto-generated>` lub `<auto-generated/>` w komentarzu w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="344ec-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="344ec-133">Może znajdować się w dowolnym wierszu tego komentarza, ale blok komentarza musi być pierwszym elementem w pliku.</span><span class="sxs-lookup"><span data-stu-id="344ec-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="344ec-134">Uruchom nazwę pliku z *TemporaryGeneratedFile_*</span><span class="sxs-lookup"><span data-stu-id="344ec-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="344ec-135">Zakończ nazwę pliku z rozszerzeniem *. Designer.cs*, *. generated.cs*, *. g.cs* lub *. g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="344ec-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="344ec-136">Generatory mogą wyrazić zgodę na użycie [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) dyrektywy preprocesora.</span><span class="sxs-lookup"><span data-stu-id="344ec-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="344ec-137">Aby ustawić tę opcję kompilatora w projekcie</span><span class="sxs-lookup"><span data-stu-id="344ec-137">To set this compiler option in a project</span></span>

<span data-ttu-id="344ec-138">Edytuj plik *. csproj* , aby dodać `<Nullable>` tag w `Project/PropertyGroup` hierarchii:</span><span class="sxs-lookup"><span data-stu-id="344ec-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="344ec-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="344ec-139">See also</span></span>

- [<span data-ttu-id="344ec-140">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="344ec-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="344ec-141">`#nullable` Dyrektywa preprocesora</span><span class="sxs-lookup"><span data-stu-id="344ec-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="344ec-142">Typy referencyjne dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="344ec-142">Nullable reference types</span></span>](../../nullable-references.md)
