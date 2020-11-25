---
title: ICorDebugReferenceValue::Dereference — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: cbcee923ecbb1106bb129f05d2e602a0fd17258d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732492"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="41ec0-102">ICorDebugReferenceValue::Dereference — Metoda</span><span class="sxs-lookup"><span data-stu-id="41ec0-102">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="41ec0-103">Pobiera obiekt, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="41ec0-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41ec0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="41ec0-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41ec0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="41ec0-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="41ec0-106">określoną Wskaźnik na adres elementu ICorDebugValue, który reprezentuje obiekt, do którego odwołuje się ten obiekt ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="41ec0-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41ec0-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="41ec0-107">Remarks</span></span>  

 <span data-ttu-id="41ec0-108">`ICorDebugValue`Obiekt jest prawidłowy tylko wtedy, gdy jego odwołanie nie zostało jeszcze wyłączone.</span><span class="sxs-lookup"><span data-stu-id="41ec0-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41ec0-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="41ec0-109">Requirements</span></span>  

 <span data-ttu-id="41ec0-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41ec0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41ec0-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="41ec0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41ec0-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="41ec0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41ec0-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41ec0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
