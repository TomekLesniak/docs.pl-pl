---
title: ICorDebugILFrame, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712394"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="db522-102">ICorDebugILFrame, interfejs</span><span class="sxs-lookup"><span data-stu-id="db522-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="db522-103">Przedstawia ramkę stosu kodu języka pośredniego firmy Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="db522-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="db522-104">Ten interfejs jest podklasą interfejsu ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="db522-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db522-105">Metody</span><span class="sxs-lookup"><span data-stu-id="db522-105">Methods</span></span>  
  
|<span data-ttu-id="db522-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="db522-106">Method</span></span>|<span data-ttu-id="db522-107">Opis</span><span class="sxs-lookup"><span data-stu-id="db522-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db522-108">CanSetIP, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="db522-109">Pobiera wartość wskazującą, czy jest bezpieczna, aby ustawić wskaźnik instrukcji na określoną lokalizację przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="db522-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="db522-110">EnumerateArguments, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="db522-111">Pobiera moduł wyliczający dla argumentów w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="db522-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="db522-112">EnumerateLocalVariables, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="db522-113">Pobiera moduł wyliczający dla zmiennych lokalnych w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="db522-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="db522-114">GetArgument, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="db522-115">Pobiera wartość określonego argumentu w tej ramce stosu MSIL.</span><span class="sxs-lookup"><span data-stu-id="db522-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="db522-116">GetIP, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="db522-117">Pobiera wartość wskaźnika instrukcji i wartość kombinacji bitowej opisującą sposób uzyskiwania wartości wskaźnika instrukcji.</span><span class="sxs-lookup"><span data-stu-id="db522-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="db522-118">GetLocalVariable, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="db522-119">Pobiera wartość określonej zmiennej lokalnej w tej ramce stosu MSIL.</span><span class="sxs-lookup"><span data-stu-id="db522-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="db522-120">GetStackDepth, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="db522-121">Nie zaimplementowano.</span><span class="sxs-lookup"><span data-stu-id="db522-121">Not implemented.</span></span>|  
|[<span data-ttu-id="db522-122">GetStackValue, metoda</span><span class="sxs-lookup"><span data-stu-id="db522-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="db522-123">Nie zaimplementowano.</span><span class="sxs-lookup"><span data-stu-id="db522-123">Not implemented.</span></span>|  
|[<span data-ttu-id="db522-124">SetIP — Metoda</span><span class="sxs-lookup"><span data-stu-id="db522-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="db522-125">Ustawia wskaźnik instrukcji na określoną lokalizację przesunięcia w kodzie MSIL.</span><span class="sxs-lookup"><span data-stu-id="db522-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db522-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="db522-126">Remarks</span></span>  

 <span data-ttu-id="db522-127">`ICorDebugILFrame`Interfejs jest wyspecjalizowanym interfejsem ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="db522-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="db522-128">Jest używana w przypadku ramek kodu MSIL lub dla ramek skompilowanych w trybie just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="db522-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="db522-129">Ramki skompilowane JIT implementują `ICorDebugILFrame` interfejs i interfejs ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="db522-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db522-130">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="db522-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db522-131">Wymagania</span><span class="sxs-lookup"><span data-stu-id="db522-131">Requirements</span></span>  

 <span data-ttu-id="db522-132">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db522-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db522-133">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="db522-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db522-134">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="db522-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db522-135">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db522-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db522-136">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="db522-136">See also</span></span>

- [<span data-ttu-id="db522-137">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="db522-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
