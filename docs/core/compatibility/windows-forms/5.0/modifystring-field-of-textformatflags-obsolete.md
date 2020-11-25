---
title: 'Nieprzerwana zmiana: TextFormatFlags. ModifyString jest przestarzała'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie pole TextFormatFlags. ModifyString jest przestarzałe jako ostrzeżenie.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761428"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="008df-103">TextFormatFlags. ModifyString jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="008df-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="008df-104"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>Pole jest przestarzałe, jako ostrzeżenie i może zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="008df-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="008df-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="008df-105">Change description</span></span>

<span data-ttu-id="008df-106">W poprzednich wersjach programu .NET <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> pole wyliczenia nie jest oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="008df-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="008df-107">W programie .NET 5,0 i jego nowszych wersjach jest oznaczona jako ostrzeżenie jako zaprzestarzała.</span><span class="sxs-lookup"><span data-stu-id="008df-107">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="008df-108">To pole może zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="008df-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="008df-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="008df-109">Reason for change</span></span>

<span data-ttu-id="008df-110">Przekazywanie ciągu do <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> przy użyciu <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> polecenia modyfikuje ciąg w niektórych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="008df-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="008df-111">To zachowanie przerywa niezmienności obietnicę i może prowadzić do krytycznego uszkodzenia stanu środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="008df-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="008df-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="008df-112">Version introduced</span></span>

<span data-ttu-id="008df-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="008df-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="008df-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="008df-114">Recommended action</span></span>

<span data-ttu-id="008df-115">Aktualizowanie dowolnego kodu, który jest zależny od <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="008df-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="008df-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="008df-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
