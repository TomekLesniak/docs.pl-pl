---
title: ICorDebugType::GetClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684463"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="f5d93-102">ICorDebugType::GetClass — Metoda</span><span class="sxs-lookup"><span data-stu-id="f5d93-102">ICorDebugType::GetClass Method</span></span>

<span data-ttu-id="f5d93-103">Pobiera wskaźnik interfejsu do ICorDebugClass, który reprezentuje typ ogólny bez wystąpień.</span><span class="sxs-lookup"><span data-stu-id="f5d93-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d93-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f5d93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5d93-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f5d93-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="f5d93-106">określoną Wskaźnik do adresu `ICorDebugClass` interfejsu, który reprezentuje typ ogólny bez wystąpień.</span><span class="sxs-lookup"><span data-stu-id="f5d93-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5d93-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f5d93-107">Remarks</span></span>  

 <span data-ttu-id="f5d93-108">`GetClass` może być wywoływana tylko w określonych warunkach.</span><span class="sxs-lookup"><span data-stu-id="f5d93-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="f5d93-109">Wywołaj metodę [ICorDebugType:: GetType](icordebugtype-gettype-method.md) przed wywołaniem metody `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="f5d93-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="f5d93-110">Jeśli `ICorDebugType::GetType` zwraca wartość CorElementType —, która jest ELEMENT_TYPE_CLASS lub ELEMENT_TYPE_VALUETYPE, `GetClass` można wywołać, aby uzyskać typ nieskonkretyzowany dla typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="f5d93-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d93-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f5d93-111">Requirements</span></span>  

 <span data-ttu-id="f5d93-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5d93-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d93-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f5d93-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5d93-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f5d93-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5d93-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d93-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
