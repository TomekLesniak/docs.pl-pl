---
title: 'Zmiana podziału: InvalidOperationException interfejsy API związane z formantem DataGridView'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, w której niektóre interfejsy API związane z formantem DataGridView zgłaszają wyjątek, jeśli wartość DataGridViewCellAccessibleObject. Owner obiektu jest równa null.
ms.date: 09/18/2020
ms.openlocfilehash: 927b1c9160700159a45aa1472b8d96f1a9ecfe25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761611"
---
# <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="6710d-103">Interfejsy API związane z formantem DataGridView teraz zgłaszają InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="6710d-103">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="6710d-104">Niektóre interfejsy API związane z teraz zgłaszają, <xref:System.Windows.Forms.DataGridView> <xref:System.InvalidOperationException> czy <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> wartość obiektu to `null` .</span><span class="sxs-lookup"><span data-stu-id="6710d-104">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

## <a name="change-description"></a><span data-ttu-id="6710d-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6710d-105">Change description</span></span>

<span data-ttu-id="6710d-106">W poprzednich wersjach platformy .NET odpowiednie interfejsy API zgłaszają, <xref:System.NullReferenceException> gdy są wywoływane, a <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> wartość to `null` .</span><span class="sxs-lookup"><span data-stu-id="6710d-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="6710d-107">Począwszy od platformy .NET 5,0, te interfejsy API zgłaszają <xref:System.InvalidOperationException> zamiast, <xref:System.NullReferenceException> Jeśli <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> wartość jest `null` wywoływana.</span><span class="sxs-lookup"><span data-stu-id="6710d-107">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="6710d-108">Zgłaszanie jest <xref:System.InvalidOperationException> zgodne z zachowaniem środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="6710d-108">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="6710d-109">Usprawnia to również środowisko debugowania przez wyraźne przekazanie nieprawidłowej właściwości.</span><span class="sxs-lookup"><span data-stu-id="6710d-109">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6710d-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6710d-110">Version introduced</span></span>

<span data-ttu-id="6710d-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6710d-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6710d-112">Recommended action</span></span>

<span data-ttu-id="6710d-113">Przejrzyj kod i, w razie potrzeby, zaktualizuj go, aby zapobiec konstruowaniu typów, których dotyczy ta <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> Właściwość jako `null` .</span><span class="sxs-lookup"><span data-stu-id="6710d-113">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6710d-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6710d-114">Affected APIs</span></span>

<span data-ttu-id="6710d-115">W poniższej tabeli wymieniono odpowiednie właściwości i parametry:</span><span class="sxs-lookup"><span data-stu-id="6710d-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="6710d-116">Zależna Metoda lub właściwość</span><span class="sxs-lookup"><span data-stu-id="6710d-116">Affected method or property</span></span> | <span data-ttu-id="6710d-117">Zweryfikowana Właściwość</span><span class="sxs-lookup"><span data-stu-id="6710d-117">Validated property</span></span> | <span data-ttu-id="6710d-118">Dodana wersja</span><span class="sxs-lookup"><span data-stu-id="6710d-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-119">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-120">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-121">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-122">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-123">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-124">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-125">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-126">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-127">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-128">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-129">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="6710d-130">5,0</span><span class="sxs-lookup"><span data-stu-id="6710d-130">5.0</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

### Category

Windows Forms

-->
