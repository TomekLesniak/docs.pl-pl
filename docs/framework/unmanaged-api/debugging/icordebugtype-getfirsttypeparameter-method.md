---
title: ICorDebugType::GetFirstTypeParameter — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: be69636056d5510b72dbce39917f5e8d3b05cd87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723977"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="2bd10-102">ICorDebugType::GetFirstTypeParameter — Metoda</span><span class="sxs-lookup"><span data-stu-id="2bd10-102">ICorDebugType::GetFirstTypeParameter Method</span></span>

<span data-ttu-id="2bd10-103">Pobiera wskaźnik interfejsu do ICorDebugType, który reprezentuje pierwszy <xref:System.Type> parametr typu reprezentowanego przez ten element `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="2bd10-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd10-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2bd10-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bd10-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2bd10-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="2bd10-106">określoną Wskaźnik do adresu `ICorDebugType` obiektu, który reprezentuje pierwszy parametr.</span><span class="sxs-lookup"><span data-stu-id="2bd10-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bd10-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2bd10-107">Remarks</span></span>  

 <span data-ttu-id="2bd10-108">`GetFirstTypeParameter` może być wywoływana w przypadkach, gdy dodatkowe informacje o typie obejmują, co najwyżej jeden parametr typu.</span><span class="sxs-lookup"><span data-stu-id="2bd10-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="2bd10-109">W szczególności można go użyć, jeśli typ jest ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF lub ELEMENT_TYPE_PTR, zgodnie z opisem przez metodę [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2bd10-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bd10-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2bd10-110">Requirements</span></span>  

 <span data-ttu-id="2bd10-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bd10-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd10-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2bd10-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bd10-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2bd10-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bd10-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd10-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
