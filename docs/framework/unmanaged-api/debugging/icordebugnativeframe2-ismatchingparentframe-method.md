---
title: ICorDebugNativeFrame2::IsMatchingParentFrame — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: 213bee96531fa0bbc9bf0ae76b2505019833abfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724705"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="68d42-102">ICorDebugNativeFrame2::IsMatchingParentFrame — Metoda</span><span class="sxs-lookup"><span data-stu-id="68d42-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>

<span data-ttu-id="68d42-103">Określa, czy określona ramka jest elementem nadrzędnym bieżącej ramki.</span><span class="sxs-lookup"><span data-stu-id="68d42-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d42-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="68d42-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68d42-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="68d42-105">Parameters</span></span>  

 `pPotentialParentFrame`  
 <span data-ttu-id="68d42-106">podczas Wskaźnik do obiektu Frame, który chcesz oszacować dla stanu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="68d42-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="68d42-107">[out] `true` Jeśli `pPotentialParentFrame` jest elementem nadrzędnym bieżącej ramki; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="68d42-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68d42-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="68d42-108">Return Value</span></span>  

 <span data-ttu-id="68d42-109">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="68d42-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="68d42-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68d42-110">HRESULT</span></span>|<span data-ttu-id="68d42-111">Opis</span><span class="sxs-lookup"><span data-stu-id="68d42-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68d42-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="68d42-112">S_OK</span></span>|<span data-ttu-id="68d42-113">Stan nadrzędny został pomyślnie zwrócony.</span><span class="sxs-lookup"><span data-stu-id="68d42-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="68d42-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68d42-114">E_FAIL</span></span>|<span data-ttu-id="68d42-115">Nie można zwrócić stanu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="68d42-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="68d42-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="68d42-116">E_INVALIDARG</span></span>|<span data-ttu-id="68d42-117">`pPotentialParentFrame` lub `pIsParent` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="68d42-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="68d42-118">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="68d42-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68d42-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="68d42-119">Remarks</span></span>  

 <span data-ttu-id="68d42-120">`IsMatchingParentFrame` zwraca `true` czy obiekt Frame przekazywany do metody jest elementem nadrzędnym obiektu Frame, dla którego Metoda została wywołana.</span><span class="sxs-lookup"><span data-stu-id="68d42-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="68d42-121">Jeśli wywołasz metodę w ramce, która nie jest elementem podrzędnym określonej ramki, zwróci błąd.</span><span class="sxs-lookup"><span data-stu-id="68d42-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d42-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="68d42-122">Requirements</span></span>  

 <span data-ttu-id="68d42-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68d42-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d42-124">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="68d42-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68d42-125">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="68d42-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68d42-126">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68d42-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d42-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="68d42-127">See also</span></span>

- [<span data-ttu-id="68d42-128">ICorDebugNativeFrame2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="68d42-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="68d42-129">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="68d42-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="68d42-130">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="68d42-130">Debugging</span></span>](index.md)
