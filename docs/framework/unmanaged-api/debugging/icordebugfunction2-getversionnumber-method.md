---
title: ICorDebugFunction2::GetVersionNumber — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 88fb205235cfaf3566fbd74b05a4e9833058f4a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696105"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="be906-102">ICorDebugFunction2::GetVersionNumber — Metoda</span><span class="sxs-lookup"><span data-stu-id="be906-102">ICorDebugFunction2::GetVersionNumber Method</span></span>

<span data-ttu-id="be906-103">Pobiera wersję Edytuj i Kontynuuj tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="be906-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be906-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="be906-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be906-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="be906-105">Parameters</span></span>  

 `pnVersion`  
 <span data-ttu-id="be906-106">określoną Wskaźnik do liczby całkowitej, która jest numerem wersji funkcji reprezentowanej przez ten obiekt ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="be906-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be906-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="be906-107">Remarks</span></span>  

 <span data-ttu-id="be906-108">Środowisko uruchomieniowe śledzi liczbę zmian, które zostały zastosowane do każdego modułu podczas sesji debugowania.</span><span class="sxs-lookup"><span data-stu-id="be906-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="be906-109">Numer wersji funkcji jest jeden więcej niż liczba edycji, która wprowadziła funkcję.</span><span class="sxs-lookup"><span data-stu-id="be906-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="be906-110">Oryginalna wersja funkcji to wersja 1.</span><span class="sxs-lookup"><span data-stu-id="be906-110">The function's original version is version 1.</span></span> <span data-ttu-id="be906-111">Liczba jest zwiększana dla modułu za każdym razem, gdy [ICorDebugModule2:: ApplyChanges —](icordebugmodule2-applychanges-method.md) jest wywoływana dla tego modułu.</span><span class="sxs-lookup"><span data-stu-id="be906-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="be906-112">Tak więc, jeśli treść funkcji została zamieniona na pierwsze i trzecie wywołanie do `ICorDebugModule2::ApplyChanges` , `GetVersionNumber` może zwrócić wersję 1, 2 lub 4 dla tej funkcji, ale nie w wersji 3.</span><span class="sxs-lookup"><span data-stu-id="be906-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="be906-113">(Ta funkcja nie ma wersji 3).</span><span class="sxs-lookup"><span data-stu-id="be906-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="be906-114">Numer wersji jest śledzony oddzielnie dla każdego modułu.</span><span class="sxs-lookup"><span data-stu-id="be906-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="be906-115">Dlatego w przypadku przeprowadzenia czterech zmian w module 1 i braku w module 2 kolejna edycja w module 1 przypisze numer wersji 6 do wszystkich edytowanych funkcji w module 1.</span><span class="sxs-lookup"><span data-stu-id="be906-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="be906-116">Jeśli ta sama Edycja obejmuje moduł 2, funkcje w module 2 uzyskają numer wersji 2.</span><span class="sxs-lookup"><span data-stu-id="be906-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="be906-117">Numer wersji uzyskany przez `GetVersionNumber` metodę może być niższy niż uzyskany przez [ICorDebugFunction:: GetCurrentVersionNumber —](icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="be906-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="be906-118">Metoda [ICorDebugCode:: GetVersionNumber —](icordebugcode-getversionnumber-method.md) wykonuje tę samą operację co `ICorDebugFunction2::GetVersionNumber` .</span><span class="sxs-lookup"><span data-stu-id="be906-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be906-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="be906-119">Requirements</span></span>  

 <span data-ttu-id="be906-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be906-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be906-121">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="be906-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be906-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="be906-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be906-123">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be906-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
