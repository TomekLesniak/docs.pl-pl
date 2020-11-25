---
title: ICorDebugILFrame::CanSetIP — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 99c80fba594e9eaf69a3cc9a025509aa4c3c26a4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703307"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="e3688-102">ICorDebugILFrame::CanSetIP — Metoda</span><span class="sxs-lookup"><span data-stu-id="e3688-102">ICorDebugILFrame::CanSetIP Method</span></span>

<span data-ttu-id="e3688-103">Pobiera wartość HRESULT, która wskazuje, czy można bezpiecznie ustawić wskaźnik instrukcji na określoną lokalizację przesunięcia w kodzie języka pośredniego (MSIL) firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3688-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3688-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e3688-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3688-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e3688-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="e3688-106">podczas Odpowiednie ustawienie wskaźnika instrukcji.</span><span class="sxs-lookup"><span data-stu-id="e3688-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3688-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e3688-107">Remarks</span></span>  

 <span data-ttu-id="e3688-108">`CanSetIP`Przed wywołaniem metody [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) Użyj metody.</span><span class="sxs-lookup"><span data-stu-id="e3688-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="e3688-109">Jeśli `CanSetIP` zwraca wartość HRESULT inną niż S_OK, można nadal wywołać `ICorDebugILFrame::SetIP` , ale nie ma gwarancji, że debuger będzie kontynuował bezpieczne i poprawia wykonywanie debugowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="e3688-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3688-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e3688-110">Requirements</span></span>  

 <span data-ttu-id="e3688-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3688-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3688-112">**Nagłówek:** CorDebug. idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="e3688-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="e3688-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e3688-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3688-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3688-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
