---
title: 'ICorDebugInstanceFieldSymbol:: GetOffset — Metoda'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724926"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="46ec5-102">ICorDebugInstanceFieldSymbol:: GetOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="46ec5-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="46ec5-103">Pobiera przesunięcie w bajtach tego pola wystąpienia w jego klasie nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="46ec5-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ec5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="46ec5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46ec5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="46ec5-105">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="46ec5-106">Wskaźnik do liczby bajtów, które to pole wystąpienia jest przesunięte w swojej klasie nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="46ec5-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ec5-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46ec5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46ec5-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="46ec5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46ec5-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="46ec5-109">Requirements</span></span>  

 <span data-ttu-id="46ec5-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46ec5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46ec5-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="46ec5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46ec5-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="46ec5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46ec5-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ec5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ec5-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="46ec5-114">See also</span></span>

- [<span data-ttu-id="46ec5-115">ICorDebugInstanceFieldSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="46ec5-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="46ec5-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="46ec5-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
