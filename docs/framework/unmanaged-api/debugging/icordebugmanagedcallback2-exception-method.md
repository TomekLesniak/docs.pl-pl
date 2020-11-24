---
title: ICorDebugManagedCallback2::Exception — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: c5be9231bcd5aaddfa0cf1b0051f8e1184faef04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687635"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="71205-102">ICorDebugManagedCallback2::Exception — Metoda</span><span class="sxs-lookup"><span data-stu-id="71205-102">ICorDebugManagedCallback2::Exception Method</span></span>

<span data-ttu-id="71205-103">Powiadamia debugera o rozpoczęciu wyszukiwania programu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="71205-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71205-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="71205-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71205-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="71205-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="71205-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą wątek, w którym został zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="71205-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="71205-107">podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek, w którym został zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="71205-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="71205-108">podczas Wskaźnik do obiektu ICorDebugFrame, który reprezentuje ramkę określoną przez `dwEventType` parametr.</span><span class="sxs-lookup"><span data-stu-id="71205-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="71205-109">Aby uzyskać więcej informacji, zobacz tabelę w sekcji uwagi.</span><span class="sxs-lookup"><span data-stu-id="71205-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="71205-110">podczas Liczba całkowita, która określa przesunięcie, zgodnie z `dwEventType` parametrem.</span><span class="sxs-lookup"><span data-stu-id="71205-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="71205-111">Aby uzyskać więcej informacji, zobacz tabelę w sekcji uwagi.</span><span class="sxs-lookup"><span data-stu-id="71205-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="71205-112">podczas Wartość wyliczenia CorDebugExceptionCallbackType —, która określa typ tego wywołania zwrotnego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="71205-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="71205-113">podczas Wartość wyliczenia [CorDebugExceptionFlags —](cordebugexceptionflags-enumeration.md) , która określa dodatkowe informacje o wyjątku</span><span class="sxs-lookup"><span data-stu-id="71205-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71205-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71205-114">Remarks</span></span>  

 <span data-ttu-id="71205-115">`Exception`Wywołanie zwrotne jest wywoływane w różnych punktach w fazie wyszukiwania procesu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="71205-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="71205-116">Oznacza to, że może być wywoływana więcej niż jeden raz podczas odwinięcia wyjątku.</span><span class="sxs-lookup"><span data-stu-id="71205-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="71205-117">Przetwarzany wyjątek można pobrać z obiektu ICorDebugThread, do którego odwołuje się `pThread` parametr.</span><span class="sxs-lookup"><span data-stu-id="71205-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="71205-118">Konkretna ramka i przesunięcie są określane przez `dwEventType` parametr w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="71205-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="71205-119">Wartość `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="71205-119">Value of `dwEventType`</span></span>|<span data-ttu-id="71205-120">Wartość `pFrame`</span><span class="sxs-lookup"><span data-stu-id="71205-120">Value of `pFrame`</span></span>|<span data-ttu-id="71205-121">Wartość `nOffset`</span><span class="sxs-lookup"><span data-stu-id="71205-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="71205-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="71205-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="71205-123">Ramka, która wywołała wyjątek.</span><span class="sxs-lookup"><span data-stu-id="71205-123">The frame that threw the exception.</span></span>|<span data-ttu-id="71205-124">Wskaźnik instrukcji w ramce.</span><span class="sxs-lookup"><span data-stu-id="71205-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="71205-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="71205-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="71205-126">Ramka kodu użytkownika najbliżej punktu zgłoszonego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="71205-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="71205-127">Wskaźnik instrukcji w ramce.</span><span class="sxs-lookup"><span data-stu-id="71205-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="71205-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="71205-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="71205-129">Ramka, która zawiera procedurę obsługi catch.</span><span class="sxs-lookup"><span data-stu-id="71205-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="71205-130">Przesunięcie języka pośredniego firmy Microsoft (MSIL) od początku procedury obsługi catch.</span><span class="sxs-lookup"><span data-stu-id="71205-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="71205-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="71205-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="71205-132">NULL</span><span class="sxs-lookup"><span data-stu-id="71205-132">NULL</span></span>|<span data-ttu-id="71205-133">Definicji.</span><span class="sxs-lookup"><span data-stu-id="71205-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71205-134">Wymagania</span><span class="sxs-lookup"><span data-stu-id="71205-134">Requirements</span></span>  

 <span data-ttu-id="71205-135">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71205-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71205-136">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="71205-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71205-137">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="71205-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71205-138">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71205-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71205-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="71205-139">See also</span></span>

- [<span data-ttu-id="71205-140">ICorDebugManagedCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="71205-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="71205-141">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="71205-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
