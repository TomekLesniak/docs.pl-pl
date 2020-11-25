---
title: ICorDebugEval::NewObjectNoConstructor — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: bb27ec755fb83dc71af7dd48b5ed6e7699436335
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729732"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="a0b03-102">ICorDebugEval::NewObjectNoConstructor — Metoda</span><span class="sxs-lookup"><span data-stu-id="a0b03-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>

<span data-ttu-id="a0b03-103">Przydziela nowe wystąpienie obiektu określonego typu, bez próby wywołania metody konstruktora.</span><span class="sxs-lookup"><span data-stu-id="a0b03-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="a0b03-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="a0b03-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a0b03-105">Zamiast tego użyj [ICorDebugEval2:: NewParameterizedObjectNoConstructor —](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a0b03-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b03-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a0b03-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b03-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="a0b03-107">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="a0b03-108">podczas Wskaźnik do obiektu ICorDebugClass, który reprezentuje typ obiektu do wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a0b03-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b03-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a0b03-109">Requirements</span></span>  

 <span data-ttu-id="a0b03-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b03-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b03-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a0b03-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0b03-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a0b03-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0b03-113">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a0b03-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b03-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a0b03-114">See also</span></span>

- [<span data-ttu-id="a0b03-115">NewParameterizedObjectNoConstructor, metoda</span><span class="sxs-lookup"><span data-stu-id="a0b03-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
