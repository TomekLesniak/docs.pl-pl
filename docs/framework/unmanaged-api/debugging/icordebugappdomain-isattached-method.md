---
title: ICorDebugAppDomain::IsAttached — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 898398b731832e698a43eb270bbdc63bb3867bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702176"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="ae7b3-102">ICorDebugAppDomain::IsAttached — Metoda</span><span class="sxs-lookup"><span data-stu-id="ae7b3-102">ICorDebugAppDomain::IsAttached Method</span></span>

<span data-ttu-id="ae7b3-103">Pobiera wartość wskazującą, czy debuger jest dołączony do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ae7b3-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7b3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ae7b3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae7b3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ae7b3-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="ae7b3-106">[out] `true` Jeśli debuger jest dołączony do domeny aplikacji; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="ae7b3-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae7b3-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ae7b3-107">Remarks</span></span>  

 <span data-ttu-id="ae7b3-108">Nie można użyć metod ICorDebugController, dopóki debuger nie dołączy do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ae7b3-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7b3-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ae7b3-109">Requirements</span></span>  

 <span data-ttu-id="ae7b3-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae7b3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7b3-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ae7b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae7b3-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ae7b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae7b3-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
