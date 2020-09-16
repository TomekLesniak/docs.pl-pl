---
title: XamlName — Gramatyka
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556697"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="98ed6-102">XamlName — Gramatyka</span><span class="sxs-lookup"><span data-stu-id="98ed6-102">XamlName Grammar</span></span>

<span data-ttu-id="98ed6-103">Gramatyka XAML to określona Gramatyka zdefiniowana w specyfikacji języka XAML [MS-XAML], która jest odtwarzana w tym miejscu dla wygody.</span><span class="sxs-lookup"><span data-stu-id="98ed6-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="98ed6-104">Ze specyfikacji języka XAML</span><span class="sxs-lookup"><span data-stu-id="98ed6-104">From the XAML Specification</span></span>

<span data-ttu-id="98ed6-105">Specyfikacja [MS-XAML] definiuje gramatykę XamlName do identyfikowania zestawu dozwolonych identyfikatorów symbolicznych używanych dla typów i właściwości.</span><span class="sxs-lookup"><span data-stu-id="98ed6-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="98ed6-106">Wartości ciągu typu XamlName muszą być zgodne z następującą gramatyką:</span><span class="sxs-lookup"><span data-stu-id="98ed6-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="98ed6-107">Który przyjmuje następujące ogólne wartości kategorii, zgodnie z definicją w bazie danych znaków Unicode</span><span class="sxs-lookup"><span data-stu-id="98ed6-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="98ed6-108">Kategoria Unicode</span><span class="sxs-lookup"><span data-stu-id="98ed6-108">Unicode category</span></span>   | <span data-ttu-id="98ed6-109">Opis</span><span class="sxs-lookup"><span data-stu-id="98ed6-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="98ed6-110">Lu</span><span class="sxs-lookup"><span data-stu-id="98ed6-110">Lu</span></span>                 | <span data-ttu-id="98ed6-111">Litera, Wielkie litery</span><span class="sxs-lookup"><span data-stu-id="98ed6-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="98ed6-112">Ll</span><span class="sxs-lookup"><span data-stu-id="98ed6-112">Ll</span></span>                 | <span data-ttu-id="98ed6-113">Litera, Małe litery</span><span class="sxs-lookup"><span data-stu-id="98ed6-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="98ed6-114">Lt</span><span class="sxs-lookup"><span data-stu-id="98ed6-114">Lt</span></span>                 | <span data-ttu-id="98ed6-115">Litera, Duże litery na początku wyrazu</span><span class="sxs-lookup"><span data-stu-id="98ed6-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="98ed6-116">Lm</span><span class="sxs-lookup"><span data-stu-id="98ed6-116">Lm</span></span>                 | <span data-ttu-id="98ed6-117">Litera, Modyfikator</span><span class="sxs-lookup"><span data-stu-id="98ed6-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="98ed6-118">Lo</span><span class="sxs-lookup"><span data-stu-id="98ed6-118">Lo</span></span>                 | <span data-ttu-id="98ed6-119">Litera, Inne</span><span class="sxs-lookup"><span data-stu-id="98ed6-119">Letter, Other</span></span>                 |
| <span data-ttu-id="98ed6-120">Mn</span><span class="sxs-lookup"><span data-stu-id="98ed6-120">Mn</span></span>                 | <span data-ttu-id="98ed6-121">Oznacz, bez odstępów</span><span class="sxs-lookup"><span data-stu-id="98ed6-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="98ed6-122">Rolę</span><span class="sxs-lookup"><span data-stu-id="98ed6-122">Mc</span></span>                 | <span data-ttu-id="98ed6-123">Znak, Odstępy mieszane</span><span class="sxs-lookup"><span data-stu-id="98ed6-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="98ed6-124">Nd</span><span class="sxs-lookup"><span data-stu-id="98ed6-124">Nd</span></span>                 | <span data-ttu-id="98ed6-125">Liczba, dziesiętna</span><span class="sxs-lookup"><span data-stu-id="98ed6-125">Number, Decimal</span></span>               |
| <span data-ttu-id="98ed6-126">NL</span><span class="sxs-lookup"><span data-stu-id="98ed6-126">Nl</span></span>                 | <span data-ttu-id="98ed6-127">Liczba, Litera</span><span class="sxs-lookup"><span data-stu-id="98ed6-127">Number, Letter</span></span>                |

<span data-ttu-id="98ed6-128">XAML definiuje drugą gramatykę, DottedXamlName, która jest używana do zakwalifikowanych odwołań do właściwości i zdarzeń, a także dla dołączonych elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="98ed6-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="98ed6-129">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.DependencyProperty> i [Omówienie języka XAML (WPF)](../fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="98ed6-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="98ed6-130">Wartości ciągu typu DottedXamlName muszą być zgodne z następującą gramatyką:</span><span class="sxs-lookup"><span data-stu-id="98ed6-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="98ed6-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="98ed6-131">Remarks</span></span>

<span data-ttu-id="98ed6-132">Aby uzyskać pełną specyfikację, zobacz [ \[ MS- \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="98ed6-132">For the complete specification, see [\[MS-XAML\]](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
