---
title: Interfejs ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713756"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="3d2af-102">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="3d2af-102">ICorDebugDataTarget2 Interface</span></span>

<span data-ttu-id="3d2af-103">Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3d2af-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d2af-104">Metody</span><span class="sxs-lookup"><span data-stu-id="3d2af-104">Methods</span></span>  
  
|<span data-ttu-id="3d2af-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-105">Method</span></span>|<span data-ttu-id="3d2af-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3d2af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d2af-107">CreateVirtualUnwinder, metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="3d2af-108">Tworzy nowy wątek unwiatrer, który zaczyna odwracać od kontekstu początkowego (co nie musi być elementem liścia wątku).</span><span class="sxs-lookup"><span data-stu-id="3d2af-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="3d2af-109">EnumerateThreadIDs, metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="3d2af-110">Zwraca listę aktywnych identyfikatorów wątków.</span><span class="sxs-lookup"><span data-stu-id="3d2af-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="3d2af-111">GetImageFromPointer, metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="3d2af-112">Zwraca adres podstawowy i rozmiar modułu z adresu w tym module.</span><span class="sxs-lookup"><span data-stu-id="3d2af-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="3d2af-113">GetImageLocation, metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="3d2af-114">Zwraca ścieżkę modułu z adresu podstawowego modułu.</span><span class="sxs-lookup"><span data-stu-id="3d2af-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="3d2af-115">GetSymbolProviderForImage, metoda</span><span class="sxs-lookup"><span data-stu-id="3d2af-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="3d2af-116">Zwraca dostawcę symboli dla modułu z adresu podstawowego tego modułu.</span><span class="sxs-lookup"><span data-stu-id="3d2af-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d2af-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3d2af-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d2af-118">Ten interfejs jest dostępny tylko dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d2af-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3d2af-119">W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="3d2af-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d2af-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3d2af-120">Requirements</span></span>  

 <span data-ttu-id="3d2af-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d2af-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d2af-122">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3d2af-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d2af-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3d2af-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d2af-124">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d2af-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2af-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3d2af-125">See also</span></span>

- [<span data-ttu-id="3d2af-126">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3d2af-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3d2af-127">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="3d2af-127">Debugging</span></span>](index.md)
