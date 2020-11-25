---
title: Interfejs ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: b9289b5afc88c926ce585a4e620364cf2dc979d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703333"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="0c0e4-102">Interfejs ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="0c0e4-102">ICorDebugILCode2 Interface</span></span>

<span data-ttu-id="0c0e4-103">[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="0c0e4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0c0e4-104">Logicznie rozszerza interfejs [ICorDebugILCode](icordebugilcode-interface.md) w celu zapewnienia metod, które zwracają token dla sygnatury zmiennej lokalnej funkcji, i mapuje przesunięcia języka pośredniego (IL) narzędzia profilera do oryginalnej metody do przesunięcia Il.</span><span class="sxs-lookup"><span data-stu-id="0c0e4-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c0e4-105">Metody</span><span class="sxs-lookup"><span data-stu-id="0c0e4-105">Methods</span></span>  
  
|<span data-ttu-id="0c0e4-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="0c0e4-106">Method</span></span>|<span data-ttu-id="0c0e4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="0c0e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c0e4-108">GetInstrumentedILMap, metoda</span><span class="sxs-lookup"><span data-stu-id="0c0e4-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="0c0e4-109">Zwraca mapę z przesunięć Instrumentacji IL do metody oryginalnej dla tego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0c0e4-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="0c0e4-110">GetLocalVarSigToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="0c0e4-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="0c0e4-111">Pobiera token metadanych lokalnej zmiennej sygnatury dla funkcji reprezentowanej przez to wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="0c0e4-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c0e4-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0c0e4-112">Requirements</span></span>  

 <span data-ttu-id="0c0e4-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c0e4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0e4-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0c0e4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c0e4-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0c0e4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c0e4-116">**.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c0e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0e4-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0c0e4-117">See also</span></span>

- [<span data-ttu-id="0c0e4-118">Interfejs ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="0c0e4-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="0c0e4-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="0c0e4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0c0e4-120">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="0c0e4-120">Debugging</span></span>](index.md)
