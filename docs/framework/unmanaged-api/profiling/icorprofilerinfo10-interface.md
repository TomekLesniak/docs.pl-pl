---
title: ICorProfilerInfo10, interfejs
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: a99fa8410bbd0dedeaeb9e1713107a3dcc9ada6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727227"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="54f95-102">ICorProfilerInfo10, interfejs</span><span class="sxs-lookup"><span data-stu-id="54f95-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="54f95-103">Podklasa elementu [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , która udostępnia metody modyfikowania funkcji IL, zapytania o informacje z środowiska uruchomieniowego oraz wstrzymywanie i wznawianie środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="54f95-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="54f95-104">Metody</span><span class="sxs-lookup"><span data-stu-id="54f95-104">Methods</span></span>  

| <span data-ttu-id="54f95-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-105">Method</span></span>|<span data-ttu-id="54f95-106">Opis</span><span class="sxs-lookup"><span data-stu-id="54f95-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="54f95-107">EnumerateObjectReferences, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="54f95-108">Podanym identyfikatorem ObjectID, wywołaniem zwrotnym i clientData, wylicza każde odwołanie do obiektu (jeśli istnieje).</span><span class="sxs-lookup"><span data-stu-id="54f95-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="54f95-109">IsFrozenObject, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="54f95-110">Przy użyciu identyfikatora ObjectID określa, czy obiekt znajduje się w segmencie tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="54f95-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="54f95-111">GetLOHObjectSizeThreshold, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="54f95-112">Pobiera wartość skonfigurowanego progu LOH.</span><span class="sxs-lookup"><span data-stu-id="54f95-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="54f95-113">RequestReJITWithInliners, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="54f95-114">ReJITs wymagane metody, a także wszystkie wbudowane metody.</span><span class="sxs-lookup"><span data-stu-id="54f95-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="54f95-115">SuspendRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="54f95-116">Wstrzymuje środowisko uruchomieniowe bez wykonywania operacji GC.</span><span class="sxs-lookup"><span data-stu-id="54f95-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="54f95-117">ResumeRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="54f95-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="54f95-118">Wznawia środowisko uruchomieniowe bez wykonywania operacji GC.</span><span class="sxs-lookup"><span data-stu-id="54f95-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="54f95-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="54f95-119">Requirements</span></span>  

<span data-ttu-id="54f95-120">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="54f95-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="54f95-121">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="54f95-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="54f95-122">**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f95-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="54f95-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="54f95-123">See also</span></span>

- [<span data-ttu-id="54f95-124">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="54f95-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
