---
title: COR_PRF_REJIT_FLAGS — Wyliczenie
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 09349674e0cf80649cc948e25a1c476c6f8097e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716372"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="4a4da-102">COR_PRF_REJIT_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="4a4da-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="4a4da-103">Zawiera wartości wskazujące, jak działa interfejs API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4a4da-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a4da-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4a4da-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4a4da-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="4a4da-105">Members</span></span>  
  
|<span data-ttu-id="4a4da-106">Członek</span><span class="sxs-lookup"><span data-stu-id="4a4da-106">Member</span></span>|<span data-ttu-id="4a4da-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4a4da-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="4a4da-108">Metody ReJITted będą blokowane przed zapisaniem ich w innych metodach.</span><span class="sxs-lookup"><span data-stu-id="4a4da-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="4a4da-109">Odbieraj `GetFunctionParameters` wywołania zwrotne dla dowolnych metod, które w sposób zażądali ReJITted.</span><span class="sxs-lookup"><span data-stu-id="4a4da-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="4a4da-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4a4da-110">Requirements</span></span>  

 <span data-ttu-id="4a4da-111">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4a4da-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="4a4da-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="4a4da-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a4da-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4a4da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a4da-114">**.NET Framework wersje:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a4da-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a4da-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4a4da-115">See also</span></span>

- [<span data-ttu-id="4a4da-116">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="4a4da-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
