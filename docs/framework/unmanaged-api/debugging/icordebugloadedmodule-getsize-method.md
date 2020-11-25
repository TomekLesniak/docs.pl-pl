---
title: ICorDebugLoadedModule::GetSize — metoda
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 2ed19cb4a190f2af7581a827e8bd11b748b3d4a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721325"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="8d562-102">ICorDebugLoadedModule::GetSize — metoda</span><span class="sxs-lookup"><span data-stu-id="8d562-102">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="8d562-103">Pobiera rozmiar w bajtach załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="8d562-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d562-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d562-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d562-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8d562-105">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="8d562-106">określoną Wskaźnik do liczby bajtów w załadowanym module.</span><span class="sxs-lookup"><span data-stu-id="8d562-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d562-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8d562-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d562-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8d562-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d562-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8d562-109">Requirements</span></span>  

 <span data-ttu-id="8d562-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d562-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d562-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8d562-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d562-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8d562-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d562-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d562-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d562-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8d562-114">See also</span></span>

- [<span data-ttu-id="8d562-115">ICorDebugLoadedModule — interfejs</span><span class="sxs-lookup"><span data-stu-id="8d562-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="8d562-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="8d562-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
