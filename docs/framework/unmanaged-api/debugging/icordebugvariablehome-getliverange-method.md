---
title: 'IcorDebugVariableHome:: GetLiveRange, Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: 4d66d09e02b907281f64400b0c605a7b5c44d476
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731049"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="27d00-102">IcorDebugVariableHome:: GetLiveRange, Metoda</span><span class="sxs-lookup"><span data-stu-id="27d00-102">IcorDebugVariableHome::GetLiveRange Method</span></span>

<span data-ttu-id="27d00-103">Pobiera natywny zakres, w którym znajduje się ta zmienna.</span><span class="sxs-lookup"><span data-stu-id="27d00-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d00-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="27d00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27d00-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="27d00-105">Parameters</span></span>  

 `pStartOffset`  
 <span data-ttu-id="27d00-106">określoną Przesunięcie logiczne, od którego zmienna jest najpierw aktywna.</span><span class="sxs-lookup"><span data-stu-id="27d00-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="27d00-107">określoną Logiczne przesunięcie bezpośrednio po punkcie, w którym zmienna jest Ostatnia na żywo.</span><span class="sxs-lookup"><span data-stu-id="27d00-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d00-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="27d00-108">Requirements</span></span>  

 <span data-ttu-id="27d00-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27d00-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27d00-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="27d00-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27d00-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="27d00-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27d00-112">**.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d00-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d00-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="27d00-113">See also</span></span>

- [<span data-ttu-id="27d00-114">ICorDebugVariableHome, interfejs</span><span class="sxs-lookup"><span data-stu-id="27d00-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
