---
title: ICorDebugLoadedModule::GetBaseAddress — metoda
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 29153da86812583a0ea789da0c0816f08e0a6b43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698081"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="d3ea3-102">ICorDebugLoadedModule::GetBaseAddress — metoda</span><span class="sxs-lookup"><span data-stu-id="d3ea3-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>

<span data-ttu-id="d3ea3-103">Pobiera adres podstawowy załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="d3ea3-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ea3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d3ea3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3ea3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d3ea3-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="d3ea3-106">określoną Wskaźnik na adres podstawowy załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="d3ea3-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3ea3-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d3ea3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3ea3-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d3ea3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ea3-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d3ea3-109">Requirements</span></span>  

 <span data-ttu-id="d3ea3-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ea3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ea3-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d3ea3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3ea3-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d3ea3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3ea3-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ea3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ea3-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d3ea3-114">See also</span></span>

- [<span data-ttu-id="d3ea3-115">ICorDebugLoadedModule — interfejs</span><span class="sxs-lookup"><span data-stu-id="d3ea3-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="d3ea3-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="d3ea3-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
