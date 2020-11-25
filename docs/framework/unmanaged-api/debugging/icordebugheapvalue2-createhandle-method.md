---
title: ICorDebugHeapValue2::CreateHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726564"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="f13de-102">ICorDebugHeapValue2::CreateHandle — Metoda</span><span class="sxs-lookup"><span data-stu-id="f13de-102">ICorDebugHeapValue2::CreateHandle Method</span></span>

<span data-ttu-id="f13de-103">Tworzy dojście określonego typu dla wartości sterty reprezentowanej przez ten obiekt ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="f13de-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f13de-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f13de-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f13de-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f13de-105">Parameters</span></span>  

 `type`  
 <span data-ttu-id="f13de-106">podczas Wartość wyliczenia CorDebugHandleType —, która określa typ dojścia do utworzenia.</span><span class="sxs-lookup"><span data-stu-id="f13de-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="f13de-107">określoną Wskaźnik do adresu obiektu ICorDebugHandleValue, który reprezentuje nowe dojście dla tej wartości sterty.</span><span class="sxs-lookup"><span data-stu-id="f13de-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f13de-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f13de-108">Remarks</span></span>  

 <span data-ttu-id="f13de-109">Dojście zostanie utworzone w domenie aplikacji skojarzonej z wartością sterty i stanie się nieprawidłowe, jeśli domena aplikacji zostanie zwolniona z ładowania.</span><span class="sxs-lookup"><span data-stu-id="f13de-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="f13de-110">Wielokrotne wywołania tej funkcji dla tej samej wartości sterty spowodują utworzenie wielu dojść.</span><span class="sxs-lookup"><span data-stu-id="f13de-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="f13de-111">Ponieważ uchwyty wpływają na wydajność modułu wyrzucania elementów bezużytecznych, debuger powinien ograniczyć się do stosunkowo niewielkiej liczby dojść (około 256), które są aktywne w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="f13de-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f13de-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f13de-112">Requirements</span></span>  

 <span data-ttu-id="f13de-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f13de-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f13de-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f13de-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f13de-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f13de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f13de-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f13de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
