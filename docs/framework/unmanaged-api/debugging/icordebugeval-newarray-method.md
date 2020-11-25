---
title: ICorDebugEval::NewArray — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: ef6cbe2cef3c52d9a4b47ff77e8aeb5159e89c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729762"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="f4152-102">ICorDebugEval::NewArray — Metoda</span><span class="sxs-lookup"><span data-stu-id="f4152-102">ICorDebugEval::NewArray Method</span></span>

<span data-ttu-id="f4152-103">Przypisuje nową tablicę określonego typu elementu i wymiarów.</span><span class="sxs-lookup"><span data-stu-id="f4152-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="f4152-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="f4152-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f4152-105">Zamiast tego użyj [ICorDebugEval2:: NewParameterizedArray —](icordebugeval2-newparameterizedarray-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f4152-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4152-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="f4152-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4152-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="f4152-107">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="f4152-108">podczas Wartość wyliczenia CorElementType —, która określa typ elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="f4152-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="f4152-109">podczas Wskaźnik do obiektu ICorDebugClass, który określa klasę elementu.</span><span class="sxs-lookup"><span data-stu-id="f4152-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="f4152-110">Ta wartość może być równa null, jeśli typ elementu jest typem pierwotnym.</span><span class="sxs-lookup"><span data-stu-id="f4152-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="f4152-111">podczas Liczba wymiarów tablicy.</span><span class="sxs-lookup"><span data-stu-id="f4152-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="f4152-112">W .NET Framework 2,0 ta wartość musi być równa 1.</span><span class="sxs-lookup"><span data-stu-id="f4152-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="f4152-113">podczas Rozmiar, w bajtach, każdego wymiaru tablicy.</span><span class="sxs-lookup"><span data-stu-id="f4152-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="f4152-114">podczas Obowiązkowe.</span><span class="sxs-lookup"><span data-stu-id="f4152-114">[in] Optional.</span></span> <span data-ttu-id="f4152-115">Dolna granica każdego wymiaru tablicy.</span><span class="sxs-lookup"><span data-stu-id="f4152-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="f4152-116">W przypadku pominięcia tej wartości dla każdego wymiaru zostanie przyjęta Dolna granica zero.</span><span class="sxs-lookup"><span data-stu-id="f4152-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4152-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f4152-117">Remarks</span></span>  

 <span data-ttu-id="f4152-118">Tablica jest zawsze tworzona w domenie aplikacji, w której jest aktualnie wykonywany wątek.</span><span class="sxs-lookup"><span data-stu-id="f4152-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4152-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f4152-119">Requirements</span></span>  

 <span data-ttu-id="f4152-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4152-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4152-121">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f4152-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4152-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f4152-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4152-123">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="f4152-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
