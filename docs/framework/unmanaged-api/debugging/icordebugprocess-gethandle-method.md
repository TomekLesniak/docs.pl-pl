---
title: ICorDebugProcess::GetHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695078"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="ceb02-102">ICorDebugProcess::GetHandle — Metoda</span><span class="sxs-lookup"><span data-stu-id="ceb02-102">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="ceb02-103">Pobiera dojście do procesu.</span><span class="sxs-lookup"><span data-stu-id="ceb02-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb02-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ceb02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb02-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ceb02-105">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="ceb02-106">określoną Wskaźnik do elementu `HPROCESS` , który jest dojściem do procesu.</span><span class="sxs-lookup"><span data-stu-id="ceb02-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ceb02-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ceb02-107">Remarks</span></span>  

 <span data-ttu-id="ceb02-108">Pobrany uchwyt jest własnością interfejsu debugowania.</span><span class="sxs-lookup"><span data-stu-id="ceb02-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="ceb02-109">Debuger powinien zduplikować dojście przed jego użyciem.</span><span class="sxs-lookup"><span data-stu-id="ceb02-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb02-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ceb02-110">Requirements</span></span>  

 <span data-ttu-id="ceb02-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb02-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb02-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ceb02-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceb02-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ceb02-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceb02-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb02-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
