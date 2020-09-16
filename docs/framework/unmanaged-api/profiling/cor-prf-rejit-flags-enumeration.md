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
ms.openlocfilehash: 1b1d6ad5d465d746f4c1a9400c43613591373322
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546949"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="9bbbb-102">COR_PRF_REJIT_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="9bbbb-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="9bbbb-103">Zawiera wartości wskazujące, jak działa interfejs API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9bbbb-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bbbb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9bbbb-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9bbbb-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="9bbbb-105">Members</span></span>  
  
|<span data-ttu-id="9bbbb-106">Członek</span><span class="sxs-lookup"><span data-stu-id="9bbbb-106">Member</span></span>|<span data-ttu-id="9bbbb-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9bbbb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="9bbbb-108">Metody ReJITted będą blokowane przed zapisaniem ich w innych metodach.</span><span class="sxs-lookup"><span data-stu-id="9bbbb-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="9bbbb-109">Odbieraj `GetFunctionParameters` wywołania zwrotne dla dowolnych metod, które w sposób zażądali ReJITted.</span><span class="sxs-lookup"><span data-stu-id="9bbbb-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="9bbbb-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9bbbb-110">Requirements</span></span>  
 <span data-ttu-id="9bbbb-111">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="9bbbb-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="9bbbb-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9bbbb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9bbbb-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9bbbb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bbbb-114">**.NET Framework wersje:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bbbb-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9bbbb-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9bbbb-115">See also</span></span>

- [<span data-ttu-id="9bbbb-116">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="9bbbb-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
