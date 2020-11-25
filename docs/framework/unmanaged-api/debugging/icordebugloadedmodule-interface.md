---
title: ICorDebugLoadedModule — interfejs
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6087411e8d23a9c3c97cb97ac8159d436e24759b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731832"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="89d8e-102">ICorDebugLoadedModule — interfejs</span><span class="sxs-lookup"><span data-stu-id="89d8e-102">ICorDebugLoadedModule Interface</span></span>

<span data-ttu-id="89d8e-103">Zawiera informacje o załadowanym module.</span><span class="sxs-lookup"><span data-stu-id="89d8e-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89d8e-104">Metody</span><span class="sxs-lookup"><span data-stu-id="89d8e-104">Methods</span></span>  
  
|<span data-ttu-id="89d8e-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="89d8e-105">Method</span></span>|<span data-ttu-id="89d8e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="89d8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89d8e-107">GetBaseAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="89d8e-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="89d8e-108">Pobiera adres podstawowy załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="89d8e-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="89d8e-109">GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="89d8e-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="89d8e-110">Pobiera nazwę załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="89d8e-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="89d8e-111">GetSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="89d8e-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="89d8e-112">Pobiera rozmiar w bajtach załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="89d8e-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89d8e-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89d8e-113">Remarks</span></span>  

 <span data-ttu-id="89d8e-114">`ICorDebugLoadedModule`Interfejs jest implementowany przez debuger i jest używany przez interfejsy debugowania CLR do uzyskiwania informacji o załadowanym module z debugera.</span><span class="sxs-lookup"><span data-stu-id="89d8e-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89d8e-115">Ten interfejs jest dostępny tylko dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89d8e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="89d8e-116">W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="89d8e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d8e-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="89d8e-117">Requirements</span></span>  

 <span data-ttu-id="89d8e-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d8e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d8e-119">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="89d8e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89d8e-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="89d8e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89d8e-121">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d8e-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d8e-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="89d8e-122">See also</span></span>

- [<span data-ttu-id="89d8e-123">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="89d8e-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="89d8e-124">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="89d8e-124">Debugging</span></span>](index.md)
