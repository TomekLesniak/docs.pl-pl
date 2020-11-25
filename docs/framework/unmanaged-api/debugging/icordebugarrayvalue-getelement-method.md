---
title: ICorDebugArrayValue::GetElement — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 0b6b6f46c7fff8f1d4c2ad555c93423f9ca8ac09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698152"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="e44a9-102">ICorDebugArrayValue::GetElement — Metoda</span><span class="sxs-lookup"><span data-stu-id="e44a9-102">ICorDebugArrayValue::GetElement Method</span></span>

<span data-ttu-id="e44a9-103">Pobiera wartość danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="e44a9-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e44a9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e44a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e44a9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e44a9-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="e44a9-106">podczas Liczba wymiarów tego `ICorDebugArrayValue` obiektu.</span><span class="sxs-lookup"><span data-stu-id="e44a9-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="e44a9-107">Ta wartość jest również rozmiarem tablicy, `indices` ponieważ jej rozmiar jest równy liczbie wymiarów `ICorDebugArrayValue` obiektu.</span><span class="sxs-lookup"><span data-stu-id="e44a9-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="e44a9-108">podczas Tablica wartości indeksu, z których każdy określa pozycję w wymiarze `ICorDebugArrayValue` obiektu.</span><span class="sxs-lookup"><span data-stu-id="e44a9-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="e44a9-109">Ta wartość nie może być równa null.</span><span class="sxs-lookup"><span data-stu-id="e44a9-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e44a9-110">określoną Wskaźnik do adresu obiektu ICorDebugValue, który reprezentuje wartość określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="e44a9-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e44a9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e44a9-111">Requirements</span></span>  

 <span data-ttu-id="e44a9-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e44a9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e44a9-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e44a9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e44a9-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e44a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e44a9-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e44a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
