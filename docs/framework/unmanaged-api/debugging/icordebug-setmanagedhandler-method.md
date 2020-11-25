---
title: ICorDebug::SetManagedHandler — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723418"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="72efb-102">ICorDebug::SetManagedHandler — Metoda</span><span class="sxs-lookup"><span data-stu-id="72efb-102">ICorDebug::SetManagedHandler Method</span></span>

<span data-ttu-id="72efb-103">Określa obiekt obsługi zdarzeń dla zdarzeń zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="72efb-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72efb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="72efb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72efb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="72efb-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="72efb-106">podczas Wskaźnik do obiektu [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , który jest obiektem procedury obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="72efb-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72efb-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="72efb-107">Remarks</span></span>  

 <span data-ttu-id="72efb-108">`SetManagedHandler` musi być wywoływana w czasie tworzenia.</span><span class="sxs-lookup"><span data-stu-id="72efb-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="72efb-109">Jeśli `ICorDebugManagedCallback` implementacja nie zawiera wystarczających interfejsów do obsługi zdarzeń debugowania dla debugowanej aplikacji, `SetManagedHandler` zwraca wartość HRESULT równą E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="72efb-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72efb-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="72efb-110">Requirements</span></span>  

 <span data-ttu-id="72efb-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72efb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72efb-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="72efb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72efb-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="72efb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72efb-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72efb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72efb-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="72efb-115">See also</span></span>

- [<span data-ttu-id="72efb-116">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="72efb-116">ICorDebug Interface</span></span>](icordebug-interface.md)
