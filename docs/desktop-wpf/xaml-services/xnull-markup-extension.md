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
# <a name="xnull-markup-extension"></a><span data-ttu-id="8eb8d-102">x:Null — Rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="8eb8d-102">x:Null Markup Extension</span></span>

<span data-ttu-id="8eb8d-103">Określa `null` jako wartość dla elementu członkowskiego języka XAML.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="8eb8d-104">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="8eb8d-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="8eb8d-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8eb8d-105">Remarks</span></span>

<span data-ttu-id="8eb8d-106">Słowo kluczowe dla odwołania o wartości null w języku C# i C++ ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="8eb8d-107">Słowo kluczowe Microsoft Visual Basic dla odwołania o wartości null to `Nothing` , ale jest zawsze używane `{x:Null}` jako użycie XAML, niezależnie od kodu związanego z kodem, który jest SKOJARZONY z XAML.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="8eb8d-108">`x:Null`Rozszerzenie znaczników nie ma właściwości settable.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="8eb8d-109">Użycie wartości null jest często kojarzone ze współczynnikiem członkowskim języka XAML dla <xref:System.Nullable%601> wartości CLR.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="8eb8d-110">`x:Null`Rozszerzenie znacznika, takie jak wszystkie rozszerzenia ZNACZNIKÓW XAML, używa nawiasów ( `{,}` ) do ucieczki obsługi wartości atrybutów, aby były inne niż literały lub odwołania do obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="8eb8d-111">Składnia atrybutu jest składnią najczęściej używaną z tym rozszerzeniem znacznika.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="8eb8d-112">Składnia elementu obiektu `<x:Null />` jest technicznie możliwa, ale rzadko jest używana, ponieważ `x:Null` rozszerzenie znaczników nie ma parametrów pozycyjnych ani argumentów konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="8eb8d-113">Aby uzyskać informacje na temat rozszerzeń znaczników, zobacz [rozszerzenia znaczników i XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="8eb8d-113">For information about markup extensions, see [Markup Extensions and WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span></span>

<span data-ttu-id="8eb8d-114">W usługach programu .NET XAML obsługa tego rozszerzenia znacznika jest definiowana przez <xref:System.Windows.Markup.NullExtension> klasę.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="8eb8d-115">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="8eb8d-115">WPF Usage Notes</span></span>

<span data-ttu-id="8eb8d-116">Należy pamiętać, że `null` nie musi być początkową wartością ustawienia dla właściwości zależności typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="8eb8d-117">Początkowa wartość domyślna może różnić się w zależności od właściwości zależności i może opierać się na metadanych specyficznych dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="8eb8d-118">Wiele właściwości zależności nie akceptuje `null` jako wartości, za pomocą znaczników ani kodu ze względu na implementacje wywołania zwrotnego walidacji.</span><span class="sxs-lookup"><span data-stu-id="8eb8d-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="8eb8d-119">Aby uzyskać więcej informacji na temat właściwości zależności, zobacz [Omówienie właściwości zależności](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span><span class="sxs-lookup"><span data-stu-id="8eb8d-119">For more information about dependency properties, see [Dependency Properties Overview](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="8eb8d-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8eb8d-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="8eb8d-121">Omówienie XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8eb8d-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="8eb8d-122">Rozszerzenia znacznikowania i WPF XAML</span><span class="sxs-lookup"><span data-stu-id="8eb8d-122">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
