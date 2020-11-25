---
title: ICorDebugThread::GetUserState — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: dd3936656ce1c9482b7f07a5780fcf651356b4be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727968"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="79b9a-102">ICorDebugThread::GetUserState — Metoda</span><span class="sxs-lookup"><span data-stu-id="79b9a-102">ICorDebugThread::GetUserState Method</span></span>

<span data-ttu-id="79b9a-103">Pobiera bieżący stan użytkownika tego ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="79b9a-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b9a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="79b9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79b9a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="79b9a-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="79b9a-106">określoną Wskaźnik do bitowej kombinacji wartości wyliczenia CorDebugUserState —, który opisują bieżący stan użytkownika tego wątku.</span><span class="sxs-lookup"><span data-stu-id="79b9a-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79b9a-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="79b9a-107">Remarks</span></span>  

 <span data-ttu-id="79b9a-108">Stanem użytkownika wątku jest stan wątku, gdy jest on sprawdzany przez debugowany program.</span><span class="sxs-lookup"><span data-stu-id="79b9a-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="79b9a-109">Wątek może mieć ustawiony wiele bitów stanu.</span><span class="sxs-lookup"><span data-stu-id="79b9a-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b9a-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="79b9a-110">Requirements</span></span>  

 <span data-ttu-id="79b9a-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b9a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b9a-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="79b9a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79b9a-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="79b9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79b9a-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79b9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
