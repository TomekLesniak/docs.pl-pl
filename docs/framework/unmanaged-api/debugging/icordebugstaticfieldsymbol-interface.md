---
title: ICorDebugStaticFieldSymbol, interfejs
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: fcf3bb61ccd903f2dd375e638814247a98aaf7b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717568"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="d27c2-102">ICorDebugStaticFieldSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="d27c2-102">ICorDebugStaticFieldSymbol Interface</span></span>

<span data-ttu-id="d27c2-103">Przedstawia informacje o symbolu debugowania dla pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="d27c2-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d27c2-104">Metody</span><span class="sxs-lookup"><span data-stu-id="d27c2-104">Methods</span></span>  
  
|<span data-ttu-id="d27c2-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="d27c2-105">Method</span></span>|<span data-ttu-id="d27c2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d27c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d27c2-107">GetAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="d27c2-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="d27c2-108">Pobiera adres pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="d27c2-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="d27c2-109">GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="d27c2-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="d27c2-110">Pobiera nazwę pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="d27c2-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="d27c2-111">GetSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="d27c2-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="d27c2-112">Pobiera rozmiar w bajtach pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="d27c2-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d27c2-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d27c2-113">Remarks</span></span>  

 <span data-ttu-id="d27c2-114">`ICorDebugStaticFieldSymbol`Interfejs jest używany do pobierania informacji o symbolach debugowania dla pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="d27c2-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d27c2-115">Ten interfejs jest dostępny tylko dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d27c2-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d27c2-116">W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="d27c2-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27c2-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d27c2-117">Requirements</span></span>  

 <span data-ttu-id="d27c2-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d27c2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27c2-119">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d27c2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27c2-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d27c2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d27c2-121">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d27c2-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27c2-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d27c2-122">See also</span></span>

- [<span data-ttu-id="d27c2-123">ICorDebugInstanceFieldSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="d27c2-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d27c2-124">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="d27c2-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d27c2-125">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="d27c2-125">Debugging</span></span>](index.md)
