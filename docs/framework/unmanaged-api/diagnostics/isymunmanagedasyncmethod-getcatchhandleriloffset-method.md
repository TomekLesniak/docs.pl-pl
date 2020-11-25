---
title: ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset — Metoda
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
ms.openlocfilehash: f5bb5f069060baa9d553d72ccf6274bbc70c2575
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707207"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="e8922-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="e8922-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>

<span data-ttu-id="e8922-103">Zobacz [DefineCatchHandlerILOffset —](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="e8922-103">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8922-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e8922-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8922-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e8922-105">Parameters</span></span>  
  
|<span data-ttu-id="e8922-106">Parametr</span><span class="sxs-lookup"><span data-stu-id="e8922-106">Parameter</span></span>|<span data-ttu-id="e8922-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e8922-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="e8922-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e8922-108">Return Value</span></span>  

 <span data-ttu-id="e8922-109">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="e8922-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8922-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e8922-110">Requirements</span></span>  

 <span data-ttu-id="e8922-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e8922-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8922-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e8922-112">See also</span></span>

- [<span data-ttu-id="e8922-113">ISymUnmanagedAsyncMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e8922-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
