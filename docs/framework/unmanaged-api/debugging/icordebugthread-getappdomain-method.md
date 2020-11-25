---
title: ICorDebugThread::GetAppDomain — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
ms.openlocfilehash: 882176f381a7c5bc4a0297021b89a96948a1cea8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728072"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="13f7f-102">ICorDebugThread::GetAppDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="13f7f-102">ICorDebugThread::GetAppDomain Method</span></span>

<span data-ttu-id="13f7f-103">Pobiera wskaźnik interfejsu do domeny aplikacji, w której jest aktualnie wykonywany ten ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="13f7f-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f7f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="13f7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13f7f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="13f7f-105">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="13f7f-106">określoną Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, w której jest aktualnie wykonywany ten wątek.</span><span class="sxs-lookup"><span data-stu-id="13f7f-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f7f-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="13f7f-107">Requirements</span></span>  

 <span data-ttu-id="13f7f-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f7f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f7f-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="13f7f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13f7f-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="13f7f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13f7f-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f7f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
