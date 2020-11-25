---
title: ICorDebugInternalFrame::GetFrameType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: c675ba4b56cecd1990184cd2f0e805250c3dfeb7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724887"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="c44cf-102">ICorDebugInternalFrame::GetFrameType — Metoda</span><span class="sxs-lookup"><span data-stu-id="c44cf-102">ICorDebugInternalFrame::GetFrameType Method</span></span>

<span data-ttu-id="c44cf-103">Pobiera typ tej wewnętrznej ramki.</span><span class="sxs-lookup"><span data-stu-id="c44cf-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44cf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c44cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c44cf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c44cf-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="c44cf-106">określoną Wskaźnik do wartości wyliczenia CorDebugInternalFrameType —, który wskazuje typ wewnętrznej ramki reprezentowanej przez ten `ICorDebugInternalFrame` obiekt.</span><span class="sxs-lookup"><span data-stu-id="c44cf-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c44cf-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c44cf-107">Remarks</span></span>  

 <span data-ttu-id="c44cf-108">Wewnętrzny typ ramki nigdy nie będzie STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="c44cf-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="c44cf-109">Debugery powinny bezpiecznie ignorować nierozpoznane typy ramek wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="c44cf-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44cf-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c44cf-110">Requirements</span></span>  

 <span data-ttu-id="c44cf-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44cf-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c44cf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c44cf-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c44cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c44cf-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
