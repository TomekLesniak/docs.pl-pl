---
title: ICorDebugManagedCallback::UnloadClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: 6efd451c6895e8fef443e2e86afa6e98279c6493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724003"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="354f8-102">ICorDebugManagedCallback::UnloadClass — Metoda</span><span class="sxs-lookup"><span data-stu-id="354f8-102">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="354f8-103">Powiadamia debuger, że Klasa jest zwalniana.</span><span class="sxs-lookup"><span data-stu-id="354f8-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354f8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="354f8-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="354f8-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="354f8-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="354f8-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą klasę.</span><span class="sxs-lookup"><span data-stu-id="354f8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="354f8-107">podczas Wskaźnik do obiektu ICorDebugClass, który reprezentuje klasę.</span><span class="sxs-lookup"><span data-stu-id="354f8-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="354f8-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="354f8-108">Remarks</span></span>  

 <span data-ttu-id="354f8-109">Nie należy odwoływać się do klasy po tym wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="354f8-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="354f8-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="354f8-110">Requirements</span></span>  

 <span data-ttu-id="354f8-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="354f8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="354f8-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="354f8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="354f8-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="354f8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="354f8-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="354f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354f8-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="354f8-115">See also</span></span>

- [<span data-ttu-id="354f8-116">LoadClass, metoda</span><span class="sxs-lookup"><span data-stu-id="354f8-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="354f8-117">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="354f8-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
