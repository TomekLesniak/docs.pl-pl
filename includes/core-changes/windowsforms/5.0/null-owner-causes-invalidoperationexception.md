---
ms.openlocfilehash: b6cb7c4b479551ff4563998f310ff518d935f48a
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656350"
---
### <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="a0f8a-101">Interfejsy API związane z formantem DataGridView teraz zgłaszają InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="a0f8a-101">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="a0f8a-102">Niektóre interfejsy API związane z teraz zgłaszają, <xref:System.Windows.Forms.DataGridView> <xref:System.InvalidOperationException> czy <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> wartość obiektu to `null` .</span><span class="sxs-lookup"><span data-stu-id="a0f8a-102">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a0f8a-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a0f8a-103">Change description</span></span>

<span data-ttu-id="a0f8a-104">W poprzednich wersjach platformy .NET odpowiednie interfejsy API zgłaszają, <xref:System.NullReferenceException> gdy są wywoływane, a <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> wartość to `null` .</span><span class="sxs-lookup"><span data-stu-id="a0f8a-104">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="a0f8a-105">Począwszy od platformy .NET 5,0, te interfejsy API zgłaszają <xref:System.InvalidOperationException> zamiast, <xref:System.NullReferenceException> Jeśli <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> wartość jest `null` wywoływana.</span><span class="sxs-lookup"><span data-stu-id="a0f8a-105">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="a0f8a-106">Zgłaszanie jest <xref:System.InvalidOperationException> zgodne z zachowaniem środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="a0f8a-106">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="a0f8a-107">Usprawnia to również środowisko debugowania przez wyraźne przekazanie nieprawidłowej właściwości.</span><span class="sxs-lookup"><span data-stu-id="a0f8a-107">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a0f8a-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a0f8a-108">Version introduced</span></span>

<span data-ttu-id="a0f8a-109">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a0f8a-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a0f8a-110">Recommended action</span></span>

<span data-ttu-id="a0f8a-111">Przejrzyj kod i, w razie potrzeby, zaktualizuj go, aby zapobiec konstruowaniu typów, których dotyczy ta <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> Właściwość jako `null` .</span><span class="sxs-lookup"><span data-stu-id="a0f8a-111">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="a0f8a-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a0f8a-112">Category</span></span>

<span data-ttu-id="a0f8a-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0f8a-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0f8a-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a0f8a-114">Affected APIs</span></span>

<span data-ttu-id="a0f8a-115">W poniższej tabeli wymieniono odpowiednie właściwości i parametry:</span><span class="sxs-lookup"><span data-stu-id="a0f8a-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="a0f8a-116">Zależna Metoda lub właściwość</span><span class="sxs-lookup"><span data-stu-id="a0f8a-116">Affected method or property</span></span> | <span data-ttu-id="a0f8a-117">Zweryfikowana Właściwość</span><span class="sxs-lookup"><span data-stu-id="a0f8a-117">Validated property</span></span> | <span data-ttu-id="a0f8a-118">Dodana wersja</span><span class="sxs-lookup"><span data-stu-id="a0f8a-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-119">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-120">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-121">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-122">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-123">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-124">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-125">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-126">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-127">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-128">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-129">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="a0f8a-130">5,0</span><span class="sxs-lookup"><span data-stu-id="a0f8a-130">5.0</span></span> |

<!-- 

#### Affected APIs

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

-->
