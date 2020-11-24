---
title: 'ICorDebugStaticFieldSymbol:: GetSize — metoda'
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 34567247935588363d96b141717d7ec07bb76546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677213"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="c5f34-102">ICorDebugStaticFieldSymbol:: GetSize — metoda</span><span class="sxs-lookup"><span data-stu-id="c5f34-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="c5f34-103">Pobiera rozmiar w bajtach pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="c5f34-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f34-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c5f34-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5f34-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c5f34-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="c5f34-106">określoną Wskaźnik do długości pola.</span><span class="sxs-lookup"><span data-stu-id="c5f34-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5f34-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5f34-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5f34-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c5f34-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f34-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c5f34-109">Requirements</span></span>  

 <span data-ttu-id="c5f34-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5f34-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f34-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c5f34-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5f34-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c5f34-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5f34-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f34-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f34-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c5f34-114">See also</span></span>

- [<span data-ttu-id="c5f34-115">ICorDebugStaticFieldSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="c5f34-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="c5f34-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="c5f34-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
