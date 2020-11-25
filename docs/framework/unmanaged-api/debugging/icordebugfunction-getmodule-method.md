---
title: ICorDebugFunction::GetModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: 5fad8b56b783748e23c8adc4aee0e1bf3450e243
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696131"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="8a421-102">ICorDebugFunction::GetModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="8a421-102">ICorDebugFunction::GetModule Method</span></span>

<span data-ttu-id="8a421-103">Pobiera moduł, w którym ta funkcja jest zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="8a421-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a421-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8a421-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a421-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8a421-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="8a421-106">określoną Wskaźnik do adresu obiektu ICorDebugModule, który reprezentuje moduł, w którym ta funkcja jest zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="8a421-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a421-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8a421-107">Requirements</span></span>  

 <span data-ttu-id="8a421-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a421-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a421-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8a421-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a421-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8a421-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a421-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a421-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
