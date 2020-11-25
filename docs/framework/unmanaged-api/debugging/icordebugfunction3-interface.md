---
title: Interfejs ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695872"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="7fc7c-102">Interfejs ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="7fc7c-102">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="7fc7c-103">[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="7fc7c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7fc7c-104">Logicznie rozszerza interfejs ICorDebugFunction w celu zapewnienia dostępu do kodu z żądania ReJIT.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fc7c-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7fc7c-105">Methods</span></span>  
  
|<span data-ttu-id="7fc7c-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="7fc7c-106">Method</span></span>|<span data-ttu-id="7fc7c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="7fc7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fc7c-108">GetActiveReJitRequestILCode, metoda</span><span class="sxs-lookup"><span data-stu-id="7fc7c-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="7fc7c-109">Pobiera wskaźnik interfejsu do [ICorDebugILCode](icordebugilcode-interface.md) zawierającego Il z aktywnego żądania ReJIT.</span><span class="sxs-lookup"><span data-stu-id="7fc7c-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fc7c-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7fc7c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc7c-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7fc7c-111">Requirements</span></span>  

 <span data-ttu-id="7fc7c-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc7c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc7c-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7fc7c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fc7c-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7fc7c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fc7c-115">**.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc7c-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7fc7c-116">See also</span></span>

- [<span data-ttu-id="7fc7c-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="7fc7c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7fc7c-118">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="7fc7c-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="7fc7c-119">ReJIT: Przewodnik How-To</span><span class="sxs-lookup"><span data-stu-id="7fc7c-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
