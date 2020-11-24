---
title: ICorDebugThread3::CreateStackWalk — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: fb9d07fffd2ec98225ce60b211f525f8dafd9725
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691072"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="ccadb-102">ICorDebugThread3::CreateStackWalk — Metoda</span><span class="sxs-lookup"><span data-stu-id="ccadb-102">ICorDebugThread3::CreateStackWalk Method</span></span>

<span data-ttu-id="ccadb-103">Tworzy obiekt [ICorDebugStackWalk](icordebugstackwalk-interface.md) dla wątku, którego stos ma zostać rozwinięcia.</span><span class="sxs-lookup"><span data-stu-id="ccadb-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccadb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ccadb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccadb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ccadb-105">Parameters</span></span>  

 `ppStackWalk`  
 <span data-ttu-id="ccadb-106">określoną Wskaźnik do adresu obiektu [ICorDebugStackWalk](icordebugstackwalk-interface.md) dla wątku, którego stos ma zostać rozwinięcia.</span><span class="sxs-lookup"><span data-stu-id="ccadb-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccadb-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ccadb-107">Return Value</span></span>  

 <span data-ttu-id="ccadb-108">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="ccadb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ccadb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccadb-109">HRESULT</span></span>|<span data-ttu-id="ccadb-110">Opis</span><span class="sxs-lookup"><span data-stu-id="ccadb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccadb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccadb-111">S_OK</span></span>|<span data-ttu-id="ccadb-112">`ICorDebugStackWalk`Obiekt został pomyślnie utworzony.</span><span class="sxs-lookup"><span data-stu-id="ccadb-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="ccadb-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccadb-113">E_FAIL</span></span>|<span data-ttu-id="ccadb-114">`ICorDebugStackWalk`Obiekt nie został utworzony.</span><span class="sxs-lookup"><span data-stu-id="ccadb-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ccadb-115">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="ccadb-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccadb-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ccadb-116">Remarks</span></span>  

 <span data-ttu-id="ccadb-117">Jeśli `CreateStackWalk` Metoda zakończy się pomyślnie, kontekst zwróconego `ICorDebugStackWalk` obiektu jest ustawiony na bieżący kontekst wątku.</span><span class="sxs-lookup"><span data-stu-id="ccadb-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccadb-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ccadb-118">Requirements</span></span>  

 <span data-ttu-id="ccadb-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccadb-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccadb-120">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ccadb-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccadb-121">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ccadb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccadb-122">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccadb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccadb-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ccadb-123">See also</span></span>

- [<span data-ttu-id="ccadb-124">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="ccadb-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ccadb-125">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="ccadb-125">Debugging</span></span>](index.md)
