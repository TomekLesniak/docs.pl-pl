---
title: ICorDebugNativeFrame::CanSetIP — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: 194065e53d550c9bbd0486de54462309a4d9ffa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695754"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="baf35-102">ICorDebugNativeFrame::CanSetIP — Metoda</span><span class="sxs-lookup"><span data-stu-id="baf35-102">ICorDebugNativeFrame::CanSetIP Method</span></span>

<span data-ttu-id="baf35-103">Pobiera wartość HRESULT, która wskazuje, czy można bezpiecznie ustawić wskaźnik instrukcji (IP) na określoną lokalizację przesunięcia w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="baf35-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf35-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="baf35-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baf35-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="baf35-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="baf35-106">podczas Odpowiednie ustawienie wskaźnika instrukcji.</span><span class="sxs-lookup"><span data-stu-id="baf35-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baf35-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="baf35-107">Remarks</span></span>  

 <span data-ttu-id="baf35-108">Użyj `CanSetIP` metody przed wywołaniem metody [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="baf35-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="baf35-109">Jeśli `CanSetIP` zwraca wartość HRESULT inną niż S_OK, można nadal wywołać `ICorDebugNativeFrame::SetIP` , ale nie ma gwarancji, że debuger będzie kontynuował bezpieczne i poprawia wykonywanie debugowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="baf35-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf35-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="baf35-110">Requirements</span></span>  

 <span data-ttu-id="baf35-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf35-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf35-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="baf35-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baf35-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="baf35-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf35-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf35-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf35-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="baf35-115">See also</span></span>
