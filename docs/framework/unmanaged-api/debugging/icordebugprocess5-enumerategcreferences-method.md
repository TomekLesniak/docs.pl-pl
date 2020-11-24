---
title: ICorDebugProcess5::EnumerateGCReferences — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 0f2f5acfc6a23398b15af3a63345050eb0dfd5b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687193"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="5bf07-102">ICorDebugProcess5::EnumerateGCReferences — Metoda</span><span class="sxs-lookup"><span data-stu-id="5bf07-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>

<span data-ttu-id="5bf07-103">Pobiera moduł wyliczający dla wszystkich obiektów, które mają być zbierane jako elementy bezużyteczne w procesie.</span><span class="sxs-lookup"><span data-stu-id="5bf07-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf07-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5bf07-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf07-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5bf07-105">Parameters</span></span>  

 `enumerateWeakReferences`  
 <span data-ttu-id="5bf07-106">podczas Wartość logiczna wskazująca, czy słabe odwołania są również wyliczane.</span><span class="sxs-lookup"><span data-stu-id="5bf07-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="5bf07-107">Jeśli `enumerateWeakReferences` ma wartość `true` , `ppEnum` moduł wyliczający zawiera zarówno silne odwołania, jak i słabe odwołania.</span><span class="sxs-lookup"><span data-stu-id="5bf07-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="5bf07-108">Jeśli `enumerateWeakReferences` ma wartość `false` , moduł wyliczający zawiera tylko silne odwołania.</span><span class="sxs-lookup"><span data-stu-id="5bf07-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="5bf07-109">określoną Wskaźnik na adres elementu [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , który jest modułem wyliczającym dla obiektów, które mają być zbierane jako elementy bezużyteczne.</span><span class="sxs-lookup"><span data-stu-id="5bf07-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf07-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5bf07-110">Remarks</span></span>  

 <span data-ttu-id="5bf07-111">Ta metoda umożliwia określenie pełnego łańcucha katalogów głównych dla dowolnego obiektu zarządzanego w procesie i może służyć do określenia, dlaczego obiekt jest nadal aktywny.</span><span class="sxs-lookup"><span data-stu-id="5bf07-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf07-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5bf07-112">Requirements</span></span>  

 <span data-ttu-id="5bf07-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf07-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf07-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5bf07-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bf07-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5bf07-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bf07-116">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf07-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5bf07-117">See also</span></span>

- [<span data-ttu-id="5bf07-118">ICorDebugProcess5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5bf07-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="5bf07-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5bf07-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
