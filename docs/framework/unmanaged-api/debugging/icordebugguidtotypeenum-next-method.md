---
title: ICorDebugGuidToTypeEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 68f548705213da7d715ae569116abae0cd24129d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705660"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="36963-102">ICorDebugGuidToTypeEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="36963-102">ICorDebugGuidToTypeEnum::Next Method</span></span>

<span data-ttu-id="36963-103">Pobiera określoną liczbę wystąpień [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) , które MAPUJĄ identyfikatory GUID na informacje o typie.</span><span class="sxs-lookup"><span data-stu-id="36963-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36963-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="36963-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36963-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="36963-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="36963-106">podczas Liczba obiektów mapowania GUID-to-Type do pobrania.</span><span class="sxs-lookup"><span data-stu-id="36963-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="36963-107">określoną Tablica wskaźników, z których każdy wskazuje obiekt [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) , który MAPUJE identyfikator GUID środowisko wykonawcze systemu Windows do odpowiadającego mu obiektu ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="36963-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="36963-108">określoną Wskaźnik do liczby obiektów [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) faktycznie zwróconych w elemencie `values` .</span><span class="sxs-lookup"><span data-stu-id="36963-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36963-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="36963-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36963-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="36963-110">Requirements</span></span>  

 <span data-ttu-id="36963-111">**Platformy:** środowisko wykonawcze systemu Windows</span><span class="sxs-lookup"><span data-stu-id="36963-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="36963-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="36963-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36963-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="36963-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36963-114">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36963-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36963-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="36963-115">See also</span></span>

- [<span data-ttu-id="36963-116">ICorDebugGuidToTypeEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="36963-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="36963-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="36963-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
