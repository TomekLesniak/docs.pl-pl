---
title: ICorDebugArrayValue::GetElementType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: 1deadef7517772460adc96cd0dd630d85cb21c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698171"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="82218-102">ICorDebugArrayValue::GetElementType — Metoda</span><span class="sxs-lookup"><span data-stu-id="82218-102">ICorDebugArrayValue::GetElementType Method</span></span>

<span data-ttu-id="82218-103">Pobiera wartość wskazującą typ prosty elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="82218-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82218-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="82218-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82218-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="82218-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="82218-106">określoną Wskaźnik do wartości wyliczenia CorElementType —, która wskazuje typ.</span><span class="sxs-lookup"><span data-stu-id="82218-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82218-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="82218-107">Requirements</span></span>  

 <span data-ttu-id="82218-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82218-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82218-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="82218-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82218-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="82218-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82218-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82218-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
