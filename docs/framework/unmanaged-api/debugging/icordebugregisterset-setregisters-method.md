---
title: ICorDebugRegisterSet::SetRegisters — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: 4be5d2d9d891010e68cd6eb96cd4456e04d8c8b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712290"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="7289a-102">ICorDebugRegisterSet::SetRegisters — Metoda</span><span class="sxs-lookup"><span data-stu-id="7289a-102">ICorDebugRegisterSet::SetRegisters Method</span></span>

<span data-ttu-id="7289a-103">`SetRegisters` nie jest zaimplementowany w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="7289a-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7289a-104">Nie wywołuj tej metody.</span><span class="sxs-lookup"><span data-stu-id="7289a-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7289a-105">Użyj operacji wyższego poziomu, takich jak [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) lub [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="7289a-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7289a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7289a-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7289a-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7289a-107">Requirements</span></span>  

 <span data-ttu-id="7289a-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7289a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7289a-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7289a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7289a-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7289a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7289a-111">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7289a-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7289a-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7289a-112">See also</span></span>

- [<span data-ttu-id="7289a-113">ICorDebugRegisterSet — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7289a-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="7289a-114">ICorDebugRegisterSet2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7289a-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
