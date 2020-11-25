---
title: 'ICorDebugMemoryBuffer:: GetStartAddress, Metoda'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710766"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="435db-102">ICorDebugMemoryBuffer:: GetStartAddress, Metoda</span><span class="sxs-lookup"><span data-stu-id="435db-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="435db-103">Pobiera początkowy adres bufora pamięci.</span><span class="sxs-lookup"><span data-stu-id="435db-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="435db-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="435db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="435db-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="435db-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="435db-106">określoną Wskaźnik do adresu początkowego bufora pamięci.</span><span class="sxs-lookup"><span data-stu-id="435db-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="435db-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="435db-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="435db-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="435db-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435db-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="435db-109">Requirements</span></span>  

 <span data-ttu-id="435db-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="435db-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435db-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="435db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="435db-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="435db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="435db-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435db-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435db-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="435db-114">See also</span></span>

- [<span data-ttu-id="435db-115">ICorDebugMemoryBuffer, interfejs</span><span class="sxs-lookup"><span data-stu-id="435db-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="435db-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="435db-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
