---
title: ICorDebugAppDomain, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 98273a5d4602c023863758045bdb2a6a502ba7a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687232"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="6ada6-102">ICorDebugAppDomain, interfejs</span><span class="sxs-lookup"><span data-stu-id="6ada6-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="6ada6-103">Dostarcza metody do debugowania domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="6ada6-104">Ten interfejs jest podklasą elementu ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="6ada6-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ada6-105">Metody</span><span class="sxs-lookup"><span data-stu-id="6ada6-105">Methods</span></span>  
  
|<span data-ttu-id="6ada6-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-106">Method</span></span>|<span data-ttu-id="6ada6-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6ada6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ada6-108">Attach, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="6ada6-109">Dołącza debuger do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-110">EnumerateAssemblies, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="6ada6-111">Pobiera moduł wyliczający dla zestawów w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-112">EnumerateBreakpoints, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="6ada6-113">Pobiera moduł wyliczający dla wszystkich aktywnych punktów przerwania w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-114">EnumerateSteppers, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="6ada6-115">Pobiera moduł wyliczający dla wszystkich aktywnych współdziałań w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-116">GetId —, Metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="6ada6-117">Pobiera unikatowy identyfikator domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-118">GetModuleFromMetaDataInterface, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="6ada6-119">Pobiera obiekt ICorDebugModule z danym interfejsem metadanych.</span><span class="sxs-lookup"><span data-stu-id="6ada6-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="6ada6-120">GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="6ada6-121">Pobiera nazwę domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-122">GetObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="6ada6-123">Pobiera wskaźnik interfejsu do domeny aplikacji środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="6ada6-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="6ada6-124">GetProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="6ada6-125">Pobiera proces zawierający domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="6ada6-126">IsAttached, metoda</span><span class="sxs-lookup"><span data-stu-id="6ada6-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="6ada6-127">Określa, czy debuger jest dołączony do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ada6-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ada6-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6ada6-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ada6-129">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="6ada6-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ada6-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6ada6-130">Requirements</span></span>  

 <span data-ttu-id="6ada6-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ada6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ada6-132">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6ada6-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ada6-133">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6ada6-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ada6-134">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ada6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ada6-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6ada6-135">See also</span></span>

- [<span data-ttu-id="6ada6-136">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="6ada6-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
