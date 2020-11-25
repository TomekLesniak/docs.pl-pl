---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: a931c15b1c4a9f099d11c43edd324cfcc2793090
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722274"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="3f93a-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT — Metoda</span><span class="sxs-lookup"><span data-stu-id="3f93a-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="3f93a-103">Pobiera wartość HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3f93a-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f93a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3f93a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f93a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3f93a-105">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="3f93a-106">określoną Wskaźnik do HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3f93a-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f93a-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3f93a-107">Return Value</span></span>  

 <span data-ttu-id="3f93a-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="3f93a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f93a-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3f93a-109">Requirements</span></span>  

 <span data-ttu-id="3f93a-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3f93a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f93a-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3f93a-111">See also</span></span>

- [<span data-ttu-id="3f93a-112">ISymUnmanagedSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f93a-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
