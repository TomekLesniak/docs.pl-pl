---
title: ICorDebugObjectEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: 8e188f304908a8029a57bb059046205c35346f3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724692"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="7ddd3-102">ICorDebugObjectEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="7ddd3-102">ICorDebugObjectEnum::Next Method</span></span>

<span data-ttu-id="7ddd3-103">Pobiera względne adresy wirtualne (RVA) określonej liczby obiektów z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="7ddd3-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddd3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7ddd3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ddd3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7ddd3-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="7ddd3-106">podczas Liczba obiektów do pobrania.</span><span class="sxs-lookup"><span data-stu-id="7ddd3-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="7ddd3-107">określoną Tablica wskaźników, z których każdy wskazuje obiekt CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="7ddd3-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7ddd3-108">określoną Wskaźnik na liczbę obiektów faktycznie zwróconych.</span><span class="sxs-lookup"><span data-stu-id="7ddd3-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="7ddd3-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="7ddd3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ddd3-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7ddd3-110">Requirements</span></span>  

 <span data-ttu-id="7ddd3-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ddd3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ddd3-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7ddd3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ddd3-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7ddd3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ddd3-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ddd3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddd3-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7ddd3-115">See also</span></span>
