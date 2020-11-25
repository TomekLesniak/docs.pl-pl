---
title: ICorDebugGenericValue::GetValue — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: dd1c1ba4a976a10d0c38c5295fff838faf072f51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728111"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="1dfe8-102">ICorDebugGenericValue::GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="1dfe8-102">ICorDebugGenericValue::GetValue Method</span></span>

<span data-ttu-id="1dfe8-103">Kopiuje wartość tego elementu generycznego do określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="1dfe8-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dfe8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1dfe8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dfe8-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1dfe8-105">Parameters</span></span>  

 `pTo`  
 <span data-ttu-id="1dfe8-106">określoną Wskaźnik do wartości, która jest reprezentowana przez ten obiekt ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="1dfe8-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="1dfe8-107">Wartość może być typem prostym lub typem referencyjnym (czyli wskaźnikiem).</span><span class="sxs-lookup"><span data-stu-id="1dfe8-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dfe8-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1dfe8-108">Requirements</span></span>  

 <span data-ttu-id="1dfe8-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dfe8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dfe8-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1dfe8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dfe8-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1dfe8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dfe8-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dfe8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
