---
title: ICorDebugILFrame::EnumerateLocalVariables — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 968ceec53aade3d04c500c8247d397ffb71382c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703203"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="9ecca-102">ICorDebugILFrame::EnumerateLocalVariables — Metoda</span><span class="sxs-lookup"><span data-stu-id="9ecca-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>

<span data-ttu-id="9ecca-103">Pobiera moduł wyliczający dla zmiennych lokalnych w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="9ecca-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ecca-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9ecca-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ecca-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9ecca-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="9ecca-106">określoną Wskaźnik do adresu obiektu ICorDebugValueEnum, który jest modułem wyliczającym dla zmiennych lokalnych w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="9ecca-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ecca-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9ecca-107">Remarks</span></span>  

 <span data-ttu-id="9ecca-108">`EnumerateLocalVariables` Pobiera moduł wyliczający, który może wyświetlać listę zmiennych lokalnych dostępnych w ramce wywołania, która jest reprezentowana przez ten obiekt ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="9ecca-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="9ecca-109">Lista nie może zawierać wszystkich zmiennych lokalnych w uruchomionej funkcji, ponieważ niektóre z nich mogą nie być aktywne.</span><span class="sxs-lookup"><span data-stu-id="9ecca-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ecca-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9ecca-110">Requirements</span></span>  

 <span data-ttu-id="9ecca-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ecca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ecca-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9ecca-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ecca-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9ecca-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ecca-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ecca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
