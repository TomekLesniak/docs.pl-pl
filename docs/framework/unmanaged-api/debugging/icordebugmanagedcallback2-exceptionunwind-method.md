---
title: ICorDebugManagedCallback2::ExceptionUnwind — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: a15391b63012fec3d0e6a0aa67540c3d2541944c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671320"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="e0aaf-102">ICorDebugManagedCallback2::ExceptionUnwind — Metoda</span><span class="sxs-lookup"><span data-stu-id="e0aaf-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>

<span data-ttu-id="e0aaf-103">Udostępnia powiadomienie o stanie podczas procesu odwracania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0aaf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e0aaf-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0aaf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e0aaf-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="e0aaf-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą wątek, w którym został zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e0aaf-107">podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek, w którym został zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="e0aaf-108">podczas Wartość wyliczenia CorDebugExceptionUnwindCallbackType —, która określa zdarzenie, które jest sygnalizowane przez wywołanie zwrotne w fazie unwind.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0aaf-109">podczas Wartość wyliczenia [CorDebugExceptionFlags —](cordebugexceptionflags-enumeration.md) , która określa dodatkowe informacje o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0aaf-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e0aaf-110">Remarks</span></span>  

 <span data-ttu-id="e0aaf-111">`ExceptionUnwind` jest wywoływana w różnych punktach w fazie unwind procesu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="e0aaf-112">`ExceptionUnwind` może być wywoływana więcej niż jeden raz podczas odwinięcia pojedynczego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="e0aaf-113">Jeśli `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, wskaźnik instrukcji będzie znajdować się w ramce liściowej wątku, w punkcie sekwencji przed (może to być kilka instrukcji przed) instrukcją, która doprowadziła do wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e0aaf-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0aaf-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e0aaf-114">Requirements</span></span>  

 <span data-ttu-id="e0aaf-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0aaf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0aaf-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e0aaf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0aaf-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e0aaf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0aaf-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0aaf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0aaf-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e0aaf-119">See also</span></span>

- [<span data-ttu-id="e0aaf-120">ICorDebugManagedCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e0aaf-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e0aaf-121">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e0aaf-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
