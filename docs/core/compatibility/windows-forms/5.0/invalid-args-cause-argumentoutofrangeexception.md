---
title: 'Zmiana istotna: właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której niektóre właściwości Windows Forms teraz zgłaszają wyjątku ArgumentOutOfRangeException dla nieprawidłowych argumentów.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761587"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="b9c47-103">Właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="b9c47-103">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="b9c47-104">Niektóre właściwości Windows Forms teraz zwracają <xref:System.ArgumentOutOfRangeException> dla nieprawidłowych argumentów, w których wcześniej nie zostały.</span><span class="sxs-lookup"><span data-stu-id="b9c47-104">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="b9c47-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="b9c47-105">Change description</span></span>

<span data-ttu-id="b9c47-106">Wcześniej te właściwości spowodowały różne wyjątki, takie jak <xref:System.NullReferenceException> , <xref:System.IndexOutOfRangeException> , lub <xref:System.ArgumentException> , gdy przekazane są argumenty poza zakresem.</span><span class="sxs-lookup"><span data-stu-id="b9c47-106">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="b9c47-107">Począwszy od platformy .NET 5,0, te właściwości generują teraz, <xref:System.ArgumentOutOfRangeException> gdy przekazane argumenty są poza zakresem.</span><span class="sxs-lookup"><span data-stu-id="b9c47-107">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="b9c47-108">Zgłaszanie jest <xref:System.ArgumentOutOfRangeException> zgodne z zachowaniem środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="b9c47-108">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="b9c47-109">Usprawnia to również środowisko debugowania, przez co jasno komunikuje się, który argument jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="b9c47-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b9c47-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b9c47-110">Version introduced</span></span>

<span data-ttu-id="b9c47-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="b9c47-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b9c47-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b9c47-112">Recommended action</span></span>

- <span data-ttu-id="b9c47-113">Zaktualizuj kod, aby zapobiec przekazywaniu nieprawidłowych argumentów.</span><span class="sxs-lookup"><span data-stu-id="b9c47-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="b9c47-114">Jeśli to konieczne, należy obsłużyć <xref:System.ArgumentOutOfRangeException> podczas ustawiania właściwości.</span><span class="sxs-lookup"><span data-stu-id="b9c47-114">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b9c47-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b9c47-115">Affected APIs</span></span>

<span data-ttu-id="b9c47-116">W poniższej tabeli wymieniono odpowiednie właściwości i parametry:</span><span class="sxs-lookup"><span data-stu-id="b9c47-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="b9c47-117">Właściwość</span><span class="sxs-lookup"><span data-stu-id="b9c47-117">Property</span></span> | <span data-ttu-id="b9c47-118">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="b9c47-118">Parameter name</span></span> | <span data-ttu-id="b9c47-119">Dodana wersja</span><span class="sxs-lookup"><span data-stu-id="b9c47-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="b9c47-120">5,0 wersja zapoznawcza 5</span><span class="sxs-lookup"><span data-stu-id="b9c47-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="b9c47-121">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="b9c47-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="b9c47-122">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="b9c47-122">5.0 Preview 6</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
