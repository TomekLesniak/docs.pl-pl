---
title: ICorDebugThread4::HadUnhandledException — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: 4e368b2c63e8e43b5c392bec4b79daac8bae249d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678542"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="9cf46-102">ICorDebugThread4::HadUnhandledException — Metoda</span><span class="sxs-lookup"><span data-stu-id="9cf46-102">ICorDebugThread4::HadUnhandledException Method</span></span>

<span data-ttu-id="9cf46-103">Wskazuje, czy wątek kiedykolwiek miał nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9cf46-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf46-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9cf46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cf46-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9cf46-105">Parameters</span></span>  

 `ppBlockingObjectEnum`  
 <span data-ttu-id="9cf46-106">określoną Wskaźnik na adres uporządkowanego wyliczania struktur [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="9cf46-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cf46-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9cf46-107">Return Value</span></span>  

 <span data-ttu-id="9cf46-108">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="9cf46-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9cf46-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cf46-109">HRESULT</span></span>|<span data-ttu-id="9cf46-110">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf46-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cf46-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cf46-111">S_OK</span></span>|<span data-ttu-id="9cf46-112">Wątek miał nieobsługiwany wyjątek od momentu jego utworzenia.</span><span class="sxs-lookup"><span data-stu-id="9cf46-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="9cf46-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9cf46-113">S_FALSE</span></span>|<span data-ttu-id="9cf46-114">Wątek nigdy nie miał nieobsłużonego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9cf46-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf46-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9cf46-115">Remarks</span></span>  

 <span data-ttu-id="9cf46-116">Ta metoda wskazuje, czy wątek kiedykolwiek miał nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9cf46-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="9cf46-117">Gdy wywołanie zwrotne nieobsłużonego wyjątku zostanie wyzwolone lub natywne dołączanie JIT jest inicjowane, ta metoda jest gwarantowana do zwrócenia S_OK.</span><span class="sxs-lookup"><span data-stu-id="9cf46-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="9cf46-118">Nie ma gwarancji, że metoda [ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md) zwróci wyjątek nieobsłużony; Jednak jeśli proces nie był jeszcze kontynuowany po otrzymaniu wywołania zwrotnego nieobsłużonego wyjątku lub po dołączeniu do natywnego kompilatora JIT.</span><span class="sxs-lookup"><span data-stu-id="9cf46-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="9cf46-119">Ponadto jest możliwe (Chociaż mało prawdopodobne), aby mieć więcej niż jeden wątek z nieobsługiwanym wyjątkiem w czasie, gdy zostanie wyzwolone Natywne Dołączanie JIT.</span><span class="sxs-lookup"><span data-stu-id="9cf46-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="9cf46-120">W takim przypadku nie ma możliwości ustalenia, który wyjątek wyzwalał dołączenie JIT.</span><span class="sxs-lookup"><span data-stu-id="9cf46-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf46-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9cf46-121">Requirements</span></span>  

 <span data-ttu-id="9cf46-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf46-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf46-123">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9cf46-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cf46-124">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9cf46-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cf46-125">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf46-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf46-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9cf46-126">See also</span></span>

- [<span data-ttu-id="9cf46-127">ICorDebugThread4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9cf46-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="9cf46-128">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9cf46-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9cf46-129">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="9cf46-129">Debugging</span></span>](index.md)
