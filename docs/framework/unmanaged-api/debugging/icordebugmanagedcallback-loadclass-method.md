---
title: ICorDebugManagedCallback::LoadClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679666"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="6f867-102">ICorDebugManagedCallback::LoadClass — Metoda</span><span class="sxs-lookup"><span data-stu-id="6f867-102">ICorDebugManagedCallback::LoadClass Method</span></span>

<span data-ttu-id="6f867-103">Powiadamia debuger o załadowaniu klasy.</span><span class="sxs-lookup"><span data-stu-id="6f867-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f867-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6f867-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f867-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6f867-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="6f867-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, do której Klasa została załadowana.</span><span class="sxs-lookup"><span data-stu-id="6f867-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="6f867-107">podczas Wskaźnik do obiektu ICorDebugClass, który reprezentuje klasę.</span><span class="sxs-lookup"><span data-stu-id="6f867-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f867-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f867-108">Remarks</span></span>  

 <span data-ttu-id="6f867-109">To wywołanie zwrotne występuje tylko wtedy, gdy dla modułu zawierającego klasę włączono funkcję ładowania klasy.</span><span class="sxs-lookup"><span data-stu-id="6f867-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="6f867-110">Ładowanie klasy jest zawsze włączone dla modułów dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="6f867-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="6f867-111">`LoadClass`Wywołanie zwrotne zapewnia odpowiedni czas na powiązanie punktów przerwania z nowo wygenerowanymi klasami w modułach dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="6f867-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f867-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6f867-112">Requirements</span></span>  

 <span data-ttu-id="6f867-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f867-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f867-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6f867-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f867-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6f867-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f867-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f867-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f867-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6f867-117">See also</span></span>

- [<span data-ttu-id="6f867-118">UnloadClass, metoda</span><span class="sxs-lookup"><span data-stu-id="6f867-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="6f867-119">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6f867-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
