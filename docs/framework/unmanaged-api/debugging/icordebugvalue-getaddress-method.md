---
title: ICorDebugValue::GetAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 47c0c4dfa78e85bcc83f0bb2a333955c8e8666fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728371"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="b0977-102">ICorDebugValue::GetAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="b0977-102">ICorDebugValue::GetAddress Method</span></span>

<span data-ttu-id="b0977-103">Pobiera adres tego obiektu "ICorDebugValue", który jest w trakcie debugowania.</span><span class="sxs-lookup"><span data-stu-id="b0977-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0977-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b0977-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0977-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b0977-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="b0977-106">określoną Wskaźnik do `CORDB_ADDRESS` obiektu, który określa adres tego obiektu wartości.</span><span class="sxs-lookup"><span data-stu-id="b0977-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0977-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b0977-107">Remarks</span></span>  

 <span data-ttu-id="b0977-108">Jeśli wartość jest niedostępna, zwracana jest wartość 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b0977-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="b0977-109">Może się tak zdarzyć, jeśli wartość jest co najmniej częściowo w rejestrach lub przechowywana w dojściu do modułu zbierającego elementy bezużyteczne ( `GCHandle` ).</span><span class="sxs-lookup"><span data-stu-id="b0977-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0977-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b0977-110">Requirements</span></span>  

 <span data-ttu-id="b0977-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0977-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0977-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b0977-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0977-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b0977-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0977-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0977-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0977-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b0977-115">See also</span></span>
