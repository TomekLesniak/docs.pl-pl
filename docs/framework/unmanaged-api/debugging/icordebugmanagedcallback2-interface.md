---
title: ICorDebugManagedCallback2 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689787"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="2d13d-102">ICorDebugManagedCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2d13d-102">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="2d13d-103">Dostarcza metody umożliwiające obsługę wyjątków debugera i obsługujące asystentów zarządzanego debugowania (MDA).</span><span class="sxs-lookup"><span data-stu-id="2d13d-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="2d13d-104">`ICorDebugManagedCallback2` jest logicznym rozszerzeniem interfejsu [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2d13d-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d13d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="2d13d-105">Methods</span></span>  
  
|<span data-ttu-id="2d13d-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-106">Method</span></span>|<span data-ttu-id="2d13d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="2d13d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d13d-108">ChangeConnection, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="2d13d-109">Powiadamia debuger o zmianie zestawu zadań skojarzonych z określonym połączeniem.</span><span class="sxs-lookup"><span data-stu-id="2d13d-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="2d13d-110">CreateConnection, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="2d13d-111">Powiadamia debuger o utworzeniu nowego połączenia.</span><span class="sxs-lookup"><span data-stu-id="2d13d-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="2d13d-112">DestroyConnection, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="2d13d-113">Powiadamia debuger o przerwaniu określonego połączenia.</span><span class="sxs-lookup"><span data-stu-id="2d13d-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="2d13d-114">Exception, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="2d13d-115">Powiadamia debugera o rozpoczęciu wyszukiwania programu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="2d13d-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="2d13d-116">ExceptionUnwind, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="2d13d-117">Udostępnia powiadomienie o stanie podczas procesu odwracania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="2d13d-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="2d13d-118">FunctionRemapComplete, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="2d13d-119">Powiadamia debuger, że wykonywanie kodu zostało przełączone do nowej wersji edytowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2d13d-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="2d13d-120">FunctionRemapOpportunity, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="2d13d-121">Powiadamia debuger, że wykonanie kodu osiągnęło punkt sekwencji w starszej wersji edytowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2d13d-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="2d13d-122">MDANotification, metoda</span><span class="sxs-lookup"><span data-stu-id="2d13d-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="2d13d-123">Zapewnia powiadomienie, że wykonanie kodu napotkało komunikat asystenta debugowania (MDA).</span><span class="sxs-lookup"><span data-stu-id="2d13d-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d13d-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2d13d-124">Remarks</span></span>  

 <span data-ttu-id="2d13d-125">`ICorDebugManagedCallback2`Interfejs rozszerza `ICorDebugManagedCallback` interfejs obsługujący nowe zdarzenia debugowania wprowadzone w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="2d13d-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="2d13d-126">Debuger musi implementować w `ICorDebugManagedCallback2` przypadku debugowania aplikacji .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="2d13d-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="2d13d-127">Wystąpienie `ICorDebugManagedCallback` lub `ICorDebugManagedCallback2` jest przesyłane jako obiekt wywołania zwrotnego do [ICorDebug:: SetManagedHandler —](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="2d13d-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d13d-128">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="2d13d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d13d-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2d13d-129">Requirements</span></span>  

 <span data-ttu-id="2d13d-130">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d13d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d13d-131">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2d13d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d13d-132">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2d13d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d13d-133">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d13d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d13d-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2d13d-134">See also</span></span>

- [<span data-ttu-id="2d13d-135">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="2d13d-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2d13d-136">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="2d13d-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2d13d-137">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2d13d-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
