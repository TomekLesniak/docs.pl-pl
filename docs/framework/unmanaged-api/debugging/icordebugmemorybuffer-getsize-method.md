---
title: 'ICorDebugMemoryBuffer:: GetSize — metoda'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710765"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="f2952-102">ICorDebugMemoryBuffer:: GetSize — metoda</span><span class="sxs-lookup"><span data-stu-id="f2952-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="f2952-103">Pobiera rozmiar buforu pamięci w bajtach.</span><span class="sxs-lookup"><span data-stu-id="f2952-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2952-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2952-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2952-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f2952-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="f2952-106">określoną Wskaźnik do rozmiaru bufora pamięci.</span><span class="sxs-lookup"><span data-stu-id="f2952-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2952-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f2952-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2952-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2952-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2952-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f2952-109">Requirements</span></span>  

 <span data-ttu-id="f2952-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2952-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2952-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2952-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2952-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f2952-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2952-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2952-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2952-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2952-114">See also</span></span>

- [<span data-ttu-id="f2952-115">ICorDebugMemoryBuffer, interfejs</span><span class="sxs-lookup"><span data-stu-id="f2952-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f2952-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f2952-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
