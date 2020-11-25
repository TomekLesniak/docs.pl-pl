---
title: ICorDebugProcess5 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717581"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="184d8-102">ICorDebugProcess5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="184d8-102">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="184d8-103">Rozszerza interfejs ICorDebugProcess w celu obsługi dostępu do sterty zarządzanej w celu zapewnienia informacji na temat wyrzucania elementów bezużytecznych obiektów zarządzanych oraz do określenia, czy debuger ładuje obrazy z lokalnej pamięci podręcznej obrazów natywnych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="184d8-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="184d8-104">Metody</span><span class="sxs-lookup"><span data-stu-id="184d8-104">Methods</span></span>  
  
|<span data-ttu-id="184d8-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-105">Method</span></span>|<span data-ttu-id="184d8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="184d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="184d8-107">EnableNGenPolicy, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="184d8-108">Ustawia wartość określającą sposób ładowania obrazów natywnych przez aplikację podczas działania w ramach zarządzanego debugera.</span><span class="sxs-lookup"><span data-stu-id="184d8-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="184d8-109">EnumerateGCReferences, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="184d8-110">Pobiera moduł wyliczający dla wszystkich obiektów, które mają być zbierane jako elementy bezużyteczne w procesie.</span><span class="sxs-lookup"><span data-stu-id="184d8-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="184d8-111">EnumerateHandles, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="184d8-112">Pobiera moduł wyliczający dla dojść do obiektów w procesie.</span><span class="sxs-lookup"><span data-stu-id="184d8-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="184d8-113">EnumerateHeap, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="184d8-114">Pobiera moduł wyliczający dla obiektów na zarządzanym stosie.</span><span class="sxs-lookup"><span data-stu-id="184d8-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="184d8-115">EnumerateHeapRegions, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="184d8-116">Pobiera moduł wyliczający dla regionów zarządzanego stosu.</span><span class="sxs-lookup"><span data-stu-id="184d8-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="184d8-117">GetArrayLayout, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="184d8-118">Pobiera informacje o układzie tablicy w pamięci.</span><span class="sxs-lookup"><span data-stu-id="184d8-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="184d8-119">GetGCHeapInformation, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="184d8-120">Pobiera wskaźnik do struktury [COR_HEAPINFO](cor-heapinfo-structure.md) , która zawiera informacje o obiektach, które mają być odzyskiwane na zarządzanym stosie.</span><span class="sxs-lookup"><span data-stu-id="184d8-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="184d8-121">GetObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="184d8-122">Pobiera wskaźnik do obiektu na zarządzanym stosie.</span><span class="sxs-lookup"><span data-stu-id="184d8-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="184d8-123">GetTypeFields, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="184d8-124">Pobiera wskaźnik do tablicy zawierającej informacje o polu dla typu na podstawie jego identyfikatora typu.</span><span class="sxs-lookup"><span data-stu-id="184d8-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="184d8-125">GetTypeForTypeID, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="184d8-126">Pobiera obiekt typu, który zawiera informacje o obiekcie w oparciu o jego identyfikatory typów.</span><span class="sxs-lookup"><span data-stu-id="184d8-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="184d8-127">GetTypeID, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="184d8-128">Pobiera identyfikator typu dla obiektu pod określonym adresem.</span><span class="sxs-lookup"><span data-stu-id="184d8-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="184d8-129">GetTypeLayout, metoda</span><span class="sxs-lookup"><span data-stu-id="184d8-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="184d8-130">Pobiera informacje o układzie obiektu w pamięci na podstawie jego identyfikatora typu.</span><span class="sxs-lookup"><span data-stu-id="184d8-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="184d8-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="184d8-131">Remarks</span></span>  

 <span data-ttu-id="184d8-132">Ten interfejs logicznie rozszerza interfejsy ICorDebugProcess, ICorDebugProcess2 i [ICorDebugProcess3](icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="184d8-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="184d8-133">Ten interfejs nie obsługuje wywoływania zdalnego, z innego komputera lub z innego procesu.</span><span class="sxs-lookup"><span data-stu-id="184d8-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="184d8-134">Wymagania</span><span class="sxs-lookup"><span data-stu-id="184d8-134">Requirements</span></span>  

 <span data-ttu-id="184d8-135">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="184d8-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="184d8-136">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="184d8-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="184d8-137">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="184d8-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="184d8-138">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="184d8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184d8-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="184d8-139">See also</span></span>

- [<span data-ttu-id="184d8-140">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="184d8-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="184d8-141">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="184d8-141">Debugging</span></span>](index.md)
