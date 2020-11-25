---
title: ICorDebugValue2::GetExactType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720363"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="6fbd1-102">ICorDebugValue2::GetExactType — Metoda</span><span class="sxs-lookup"><span data-stu-id="6fbd1-102">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="6fbd1-103">Pobiera wskaźnik interfejsu do obiektu "ICorDebugType", który reprezentuje <xref:System.Type> tę wartość.</span><span class="sxs-lookup"><span data-stu-id="6fbd1-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fbd1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6fbd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fbd1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6fbd1-105">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="6fbd1-106">określoną Wskaźnik do adresu `ICorDebugType` obiektu, który reprezentuje <xref:System.Type> wartość reprezentowaną przez ten obiekt "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="6fbd1-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fbd1-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6fbd1-107">Remarks</span></span>  

 <span data-ttu-id="6fbd1-108">Metoda oparta na typach ogólnych `GetExactType` zastępuje metody [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) i [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , z których każdy zwraca informacje o typie wartości.</span><span class="sxs-lookup"><span data-stu-id="6fbd1-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fbd1-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6fbd1-109">Requirements</span></span>  

 <span data-ttu-id="6fbd1-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fbd1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fbd1-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6fbd1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fbd1-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6fbd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fbd1-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fbd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbd1-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6fbd1-114">See also</span></span>
