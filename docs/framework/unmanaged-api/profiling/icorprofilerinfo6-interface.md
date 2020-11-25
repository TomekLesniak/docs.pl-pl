---
title: ICorProfilerInfo6, interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: b3aed97e19694675fd5e0c1070dbbf6d9321eedd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733844"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="39517-102">ICorProfilerInfo6, interfejs</span><span class="sxs-lookup"><span data-stu-id="39517-102">ICorProfilerInfo6 Interface</span></span>

<span data-ttu-id="39517-103">[Obsługiwane w .NET Framework 4,6 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="39517-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="39517-104">Podklasa elementu [ICorProfilerInfo5](icorprofilerinfo5-interface.md) , która dostarcza moduł wyliczający dla wszystkich metod, które są zdefiniowane w danym module NGen i w sposób wbudowany daną metodę.</span><span class="sxs-lookup"><span data-stu-id="39517-104">A subclass of [ICorProfilerInfo5](icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39517-105">Metody</span><span class="sxs-lookup"><span data-stu-id="39517-105">Methods</span></span>  
  
|<span data-ttu-id="39517-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="39517-106">Method</span></span>|<span data-ttu-id="39517-107">Opis</span><span class="sxs-lookup"><span data-stu-id="39517-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39517-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod, metoda</span><span class="sxs-lookup"><span data-stu-id="39517-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="39517-109">Zwraca moduł wyliczający dla wszystkich metod, które należą do danego modułu NGen i są zawarte w treści danej metody.</span><span class="sxs-lookup"><span data-stu-id="39517-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39517-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="39517-110">Requirements</span></span>  

 <span data-ttu-id="39517-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39517-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39517-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="39517-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39517-113">**.NET Framework wersje:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39517-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39517-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="39517-114">See also</span></span>

- [<span data-ttu-id="39517-115">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="39517-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
