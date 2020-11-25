---
title: 'ICorDebugVariableHome:: GetOffset — Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711796"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="7d71b-102">ICorDebugVariableHome:: GetOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="7d71b-102">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="7d71b-103">Pobiera przesunięcie z rejestru podstawowego dla zmiennej.</span><span class="sxs-lookup"><span data-stu-id="7d71b-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d71b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d71b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d71b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7d71b-105">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="7d71b-106">określoną Przesunięcie od podstawowego rejestru.</span><span class="sxs-lookup"><span data-stu-id="7d71b-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d71b-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7d71b-107">Return Value</span></span>  

 <span data-ttu-id="7d71b-108">Metoda zwraca następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="7d71b-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="7d71b-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="7d71b-109">Value</span></span>|<span data-ttu-id="7d71b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="7d71b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="7d71b-111">Zmienna znajduje się w lokalizacji pamięci względnej do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="7d71b-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="7d71b-112">Zmienna nie znajduje się w lokalizacji pamięci względnej do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="7d71b-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d71b-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d71b-113">Requirements</span></span>  

 <span data-ttu-id="7d71b-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d71b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d71b-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7d71b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d71b-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7d71b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d71b-117">**.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d71b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d71b-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7d71b-118">See also</span></span>

- [<span data-ttu-id="7d71b-119">ICorDebugVariableHome, interfejs</span><span class="sxs-lookup"><span data-stu-id="7d71b-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
