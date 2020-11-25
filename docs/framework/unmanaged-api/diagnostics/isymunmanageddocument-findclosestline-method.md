---
title: ISymUnmanagedDocument::FindClosestLine — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 5ec67758e3174493cbd5cec1de0dcce30013ac43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698588"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="fc531-102">ISymUnmanagedDocument::FindClosestLine — Metoda</span><span class="sxs-lookup"><span data-stu-id="fc531-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="fc531-103">Zwraca najbliższy wiersz będący punktem sekwencji, uwzględniając wiersz w tym dokumencie, który może lub nie jest punktem sekwencji.</span><span class="sxs-lookup"><span data-stu-id="fc531-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc531-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fc531-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc531-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fc531-105">Parameters</span></span>  

 `line`  
 <span data-ttu-id="fc531-106">podczas Wiersz w tym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="fc531-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc531-107">określoną Wskaźnik do zmiennej, która otrzymuje wiersz.</span><span class="sxs-lookup"><span data-stu-id="fc531-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc531-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="fc531-108">Return Value</span></span>  

 <span data-ttu-id="fc531-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie kod błędu.</span><span class="sxs-lookup"><span data-stu-id="fc531-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc531-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fc531-110">See also</span></span>

- [<span data-ttu-id="fc531-111">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fc531-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
