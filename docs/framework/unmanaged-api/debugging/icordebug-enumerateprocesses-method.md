---
title: ICorDebug::EnumerateProcesses — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: bf672c90cdbb9e9fb66105820a264a49601b38d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723457"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="d4285-102">ICorDebug::EnumerateProcesses — Metoda</span><span class="sxs-lookup"><span data-stu-id="d4285-102">ICorDebug::EnumerateProcesses Method</span></span>

<span data-ttu-id="d4285-103">Pobiera moduł wyliczający dla procesów, które są debugowane.</span><span class="sxs-lookup"><span data-stu-id="d4285-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4285-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4285-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4285-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d4285-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="d4285-106">Wskaźnik do adresu obiektu ICorDebugProcessEnum, który jest modułem wyliczającym dla debugowanych procesów.</span><span class="sxs-lookup"><span data-stu-id="d4285-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4285-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4285-107">Requirements</span></span>  

 <span data-ttu-id="d4285-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4285-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4285-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d4285-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4285-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d4285-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4285-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4285-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4285-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d4285-112">See also</span></span>

- [<span data-ttu-id="d4285-113">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d4285-113">ICorDebug Interface</span></span>](icordebug-interface.md)
