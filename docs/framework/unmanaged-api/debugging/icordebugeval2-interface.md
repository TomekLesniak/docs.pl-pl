---
title: ICorDebugEval2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: 090b587ef509795609250914ce8883ad96d28c18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729684"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="5e3ce-102">ICorDebugEval2, interfejs</span><span class="sxs-lookup"><span data-stu-id="5e3ce-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="5e3ce-103">Rozszerza "ICorDebugEval", aby zapewnić obsługę typów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e3ce-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5e3ce-104">Methods</span></span>  
  
|<span data-ttu-id="5e3ce-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-105">Method</span></span>|<span data-ttu-id="5e3ce-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5e3ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e3ce-107">CallParameterizedFunction, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="5e3ce-108">Konfiguruje wywołanie do określonego elementu "ICorDebugFunction", który może być zagnieżdżony wewnątrz typu, którego Konstruktor pobiera parametry typu, lub sam może przyjmować parametry typu.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="5e3ce-109">CreateValueForType, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="5e3ce-110">Pobiera wskaźnik do nowego elementu "ICorDebugValue" określonego typu z początkową wartością null lub zero.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="5e3ce-111">NewParameterizedArray, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="5e3ce-112">Przypisuje nową tablicę określonego typu elementu i wymiarów.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="5e3ce-113">NewParameterizedObject, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="5e3ce-114">Tworzy wystąpienie nowego obiektu typu sparametryzowanego i wywołuje metodę konstruktora obiektu.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="5e3ce-115">NewParameterizedObjectNoConstructor, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="5e3ce-116">Tworzy wystąpienie nowego obiektu typu sparametryzowanego określonej klasy bez próby wywołania metody konstruktora</span><span class="sxs-lookup"><span data-stu-id="5e3ce-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="5e3ce-117">NewStringWithLength, metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="5e3ce-118">Tworzy nowy ciąg o określonej długości z określoną zawartością.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="5e3ce-119">RudeAbort — Metoda</span><span class="sxs-lookup"><span data-stu-id="5e3ce-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="5e3ce-120">Przerywa obliczenia, które `ICorDebugEval2` jest aktualnie wykonywane.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e3ce-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5e3ce-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e3ce-122">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="5e3ce-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e3ce-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5e3ce-123">Requirements</span></span>  

 <span data-ttu-id="5e3ce-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e3ce-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e3ce-125">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5e3ce-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e3ce-126">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5e3ce-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e3ce-127">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e3ce-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3ce-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5e3ce-128">See also</span></span>

- [<span data-ttu-id="5e3ce-129">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5e3ce-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
