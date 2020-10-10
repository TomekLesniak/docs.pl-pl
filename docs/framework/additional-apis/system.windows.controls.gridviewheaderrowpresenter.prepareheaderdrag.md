---
title: Metoda PrepareHeaderDrag (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Dowiedz się więcej o metodzie prywatnej WPF o nazwie PrepareHeaderDrag.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877766"
---
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="fc0cd-103">PrepareHeaderDrag, Metoda</span><span class="sxs-lookup"><span data-stu-id="fc0cd-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="fc0cd-104">Przygotowuje określony nagłówek kolumny dla zmiany kolejności.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="fc0cd-105">Ta metoda jest prywatna i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fc0cd-106">Firma Microsoft nie obsługuje korzystania z tej metody w aplikacji produkcyjnej w żadnej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="fc0cd-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="fc0cd-107">Parameters</span></span>

<span data-ttu-id="fc0cd-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="fc0cd-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="fc0cd-109">Nagłówek kolumny, aby przygotować się do zmiany kolejności.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="fc0cd-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="fc0cd-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="fc0cd-111">Pozycja, względem <xref:System.Windows.Controls.GridViewHeaderRowPresenter> której rozpocznie się przeciąganie.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="fc0cd-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="fc0cd-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="fc0cd-113">Pozycja, względem `header` której rozpocznie się przeciąganie.</span><span class="sxs-lookup"><span data-stu-id="fc0cd-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="fc0cd-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="fc0cd-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="fc0cd-115">`true` Aby anulować zmianę kolejności; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="fc0cd-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc0cd-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fc0cd-116">Requirements</span></span>

<span data-ttu-id="fc0cd-117">**Przestrzeń nazw:**<xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="fc0cd-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="fc0cd-118">**Zestaw:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="fc0cd-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="fc0cd-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fc0cd-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
