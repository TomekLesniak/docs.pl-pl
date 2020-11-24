---
title: ICorDebugThread::CreateStepper — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688279"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="fef5d-102">ICorDebugThread::CreateStepper — Metoda</span><span class="sxs-lookup"><span data-stu-id="fef5d-102">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="fef5d-103">Tworzy obiekt ICorDebugStepper, który umożliwia przechodzenie przez aktywną ramkę tego ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fef5d-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef5d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fef5d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fef5d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fef5d-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="fef5d-106">określoną Wskaźnik do adresu `ICorDebugStepper` obiektu, który umożliwia przechodzenie przez aktywną ramkę tego wątku.</span><span class="sxs-lookup"><span data-stu-id="fef5d-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fef5d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fef5d-107">Remarks</span></span>  

 <span data-ttu-id="fef5d-108">Aktywna ramka może być kodem niezarządzanym.</span><span class="sxs-lookup"><span data-stu-id="fef5d-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="fef5d-109">`ICorDebugStepper`Interfejs musi być używany do wykonywania rzeczywistego kroku.</span><span class="sxs-lookup"><span data-stu-id="fef5d-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef5d-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fef5d-110">Requirements</span></span>  

 <span data-ttu-id="fef5d-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef5d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef5d-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fef5d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fef5d-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fef5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fef5d-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
