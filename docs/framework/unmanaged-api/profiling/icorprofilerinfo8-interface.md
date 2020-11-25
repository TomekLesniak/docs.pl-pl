---
title: ICorProfilerInfo8, interfejs
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: eedd16006781de517587e5138543b9b9eca3ff90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733610"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="ef328-102">ICorProfilerInfo8, interfejs</span><span class="sxs-lookup"><span data-stu-id="ef328-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="ef328-103">Podklasa elementu [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , która dostarcza metody do badania informacji o metodach dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="ef328-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="ef328-104">Metody</span><span class="sxs-lookup"><span data-stu-id="ef328-104">Methods</span></span>  

| <span data-ttu-id="ef328-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="ef328-105">Method</span></span>|<span data-ttu-id="ef328-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ef328-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="ef328-107">IsFunctionDynamic, metoda</span><span class="sxs-lookup"><span data-stu-id="ef328-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="ef328-108">Określa, czy funkcja nie ma skojarzonych metadanych.</span><span class="sxs-lookup"><span data-stu-id="ef328-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="ef328-109">GetFunctionFromIP3, metoda</span><span class="sxs-lookup"><span data-stu-id="ef328-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="ef328-110">Mapuje wskaźnik zarządzanej instrukcji kodu na FunctionID.</span><span class="sxs-lookup"><span data-stu-id="ef328-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="ef328-111">Ta metoda działa w przypadku metod dynamicznych i niedynamicznych.</span><span class="sxs-lookup"><span data-stu-id="ef328-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="ef328-112">GetDynamicFunctionInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="ef328-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="ef328-113">Pobiera informacje o metodach dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="ef328-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ef328-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ef328-114">Requirements</span></span>  

<span data-ttu-id="ef328-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef328-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ef328-116">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="ef328-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="ef328-117">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef328-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ef328-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ef328-118">See also</span></span>

- [<span data-ttu-id="ef328-119">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="ef328-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
