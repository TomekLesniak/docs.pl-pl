---
title: Metoda FindHeaderByColumn (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Dowiedz się więcej o metodzie prywatnej WPF o nazwie FindHeaderByColumn.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877773"
---
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="96ed4-103">FindHeaderByColumn, Metoda</span><span class="sxs-lookup"><span data-stu-id="96ed4-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="96ed4-104">Znajduje nagłówek kolumny dla określonej kolumny w drzewie wizualnym.</span><span class="sxs-lookup"><span data-stu-id="96ed4-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="96ed4-105">Ta metoda jest prywatna i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="96ed4-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="96ed4-106">Firma Microsoft nie obsługuje korzystania z tej metody w aplikacji produkcyjnej w żadnej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="96ed4-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="96ed4-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="96ed4-107">Parameters</span></span>

<span data-ttu-id="96ed4-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="96ed4-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="96ed4-109">Kolumna, której nagłówek ma być znaleziony i zwrócony.</span><span class="sxs-lookup"><span data-stu-id="96ed4-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="96ed4-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="96ed4-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="96ed4-111">Nagłówek określonej kolumny lub `null` Jeśli określona kolumna nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="96ed4-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="96ed4-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="96ed4-112">Requirements</span></span>

<span data-ttu-id="96ed4-113">**Przestrzeń nazw:**<xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="96ed4-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="96ed4-114">**Zestaw:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="96ed4-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="96ed4-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96ed4-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
