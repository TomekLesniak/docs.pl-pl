---
title: ICorDebugFrame::GetCallee — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 6347e0109f256dc46eb0140ffd1f51977c205b51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678808"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="8c739-102">ICorDebugFrame::GetCallee — Metoda</span><span class="sxs-lookup"><span data-stu-id="8c739-102">ICorDebugFrame::GetCallee Method</span></span>

<span data-ttu-id="8c739-103">Pobiera wskaźnik do obiektu ICorDebugFrame w bieżącym łańcuchu, dla którego ta ramka została wywołana.</span><span class="sxs-lookup"><span data-stu-id="8c739-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c739-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8c739-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c739-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8c739-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="8c739-106">określoną Wskaźnik do adresu `ICorDebugFrame` obiektu, który reprezentuje wywoływaną ramkę.</span><span class="sxs-lookup"><span data-stu-id="8c739-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="8c739-107">Ta wartość jest równa null, jeśli wywoływana ramka jest wewnętrzna ramką w bieżącym łańcuchu.</span><span class="sxs-lookup"><span data-stu-id="8c739-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c739-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8c739-108">Requirements</span></span>  

 <span data-ttu-id="8c739-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c739-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c739-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8c739-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c739-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8c739-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c739-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c739-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
