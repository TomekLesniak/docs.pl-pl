---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 9803094753dee27318af9981bd2e2ad196d434e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729073"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="7d067-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength — Metoda</span><span class="sxs-lookup"><span data-stu-id="7d067-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>

<span data-ttu-id="7d067-103">Pobiera długość ścieżki wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="7d067-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d067-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d067-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d067-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7d067-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="7d067-106">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora wymaganego do przechowywania długości ścieżki wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="7d067-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d067-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7d067-107">Return Value</span></span>  

 <span data-ttu-id="7d067-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="7d067-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d067-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d067-109">Requirements</span></span>  

 <span data-ttu-id="7d067-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7d067-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d067-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7d067-111">See also</span></span>

- [<span data-ttu-id="7d067-112">ISymUnmanagedSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7d067-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
