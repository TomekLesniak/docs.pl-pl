---
title: 'Nieprzerwana zmiana: Usunięto kontrolki paska stanu'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której niektóre kontrolki Windows Forms nie są już dostępne.
ms.date: 07/18/2020
ms.openlocfilehash: 70aaa20f3fee1f4c342c4d9e547b0658aaf533b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761608"
---
# <a name="removed-status-bar-controls"></a><span data-ttu-id="f2cf8-103">Usunięto kontrolki paska stanu</span><span class="sxs-lookup"><span data-stu-id="f2cf8-103">Removed status bar controls</span></span>

<span data-ttu-id="f2cf8-104">Począwszy od platformy .NET 5,0, niektóre kontrolki Windows Forms nie są już dostępne.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-104">Starting in .NET 5.0, some Windows Forms controls are no longer available.</span></span>

## <a name="change-description"></a><span data-ttu-id="f2cf8-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="f2cf8-105">Change description</span></span>

<span data-ttu-id="f2cf8-106">Począwszy od platformy .NET 5,0, niektóre kontrolki Windows Forms powiązane z paskiem stanu nie są już dostępne.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-106">Starting with .NET 5.0, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="f2cf8-107">Kontrolki zamiany, które mają lepszy projekt i pomoc techniczną, zostały wprowadzone w .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-107">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="f2cf8-108">Przestarzałe formanty zostały wcześniej usunięte z przyborników projektanta, ale były nadal dostępne do użycia.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-108">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="f2cf8-109">Teraz zostały całkowicie usunięte.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-109">Now, they have been completely removed.</span></span>

<span data-ttu-id="f2cf8-110">Następujące typy nie są już dostępne:</span><span class="sxs-lookup"><span data-stu-id="f2cf8-110">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a><span data-ttu-id="f2cf8-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f2cf8-111">Version introduced</span></span>

<span data-ttu-id="f2cf8-112">5,0</span><span class="sxs-lookup"><span data-stu-id="f2cf8-112">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f2cf8-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="f2cf8-113">Recommended action</span></span>

<span data-ttu-id="f2cf8-114">Przejdź do zastępczych interfejsów API dla tych formantów i ich scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="f2cf8-114">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="f2cf8-115">Stara kontrolka (API)</span><span class="sxs-lookup"><span data-stu-id="f2cf8-115">Old Control (API)</span></span> | <span data-ttu-id="f2cf8-116">Zalecane zastąpienie</span><span class="sxs-lookup"><span data-stu-id="f2cf8-116">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="f2cf8-117">StatusBar</span><span class="sxs-lookup"><span data-stu-id="f2cf8-117">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="f2cf8-118">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="f2cf8-118">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a><span data-ttu-id="f2cf8-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f2cf8-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle`

### Category

Windows Forms

-->
