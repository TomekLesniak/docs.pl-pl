---
title: ICorDebugValue3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 419efc7f21f4ac2e68657b2a4d69a8690a2938d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722313"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="e72c5-102">ICorDebugValue3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e72c5-102">ICorDebugValue3 Interface</span></span>

<span data-ttu-id="e72c5-103">Rozszerza interfejsy "ICorDebugValue" i "ICorDebugValue2", aby zapewnić obsługę tablic o rozmiarze większym niż 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e72c5-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e72c5-104">Metody</span><span class="sxs-lookup"><span data-stu-id="e72c5-104">Methods</span></span>  
  
|<span data-ttu-id="e72c5-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="e72c5-105">Method</span></span>|<span data-ttu-id="e72c5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e72c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e72c5-107">GetSize64, metoda</span><span class="sxs-lookup"><span data-stu-id="e72c5-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="e72c5-108">Pobiera rozmiar tego obiektu w bajtach `ICorDebugValue3` .</span><span class="sxs-lookup"><span data-stu-id="e72c5-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e72c5-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e72c5-109">Remarks</span></span>  

 <span data-ttu-id="e72c5-110">Metoda [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) zwraca rozmiar obiektu, który mieści się w zakresie od 0 do 2 147 483 647 bajtów.</span><span class="sxs-lookup"><span data-stu-id="e72c5-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="e72c5-111">W .NET Framework 4,5 rozmiar tablic może przekroczyć 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e72c5-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="e72c5-112">`ICorDebugValue3`Interfejs umożliwia określenie rozmiaru tych tablic.</span><span class="sxs-lookup"><span data-stu-id="e72c5-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e72c5-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e72c5-113">Requirements</span></span>  

 <span data-ttu-id="e72c5-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e72c5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e72c5-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e72c5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e72c5-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e72c5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e72c5-117">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e72c5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e72c5-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e72c5-118">See also</span></span>

- [<span data-ttu-id="e72c5-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="e72c5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e72c5-120">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="e72c5-120">Debugging</span></span>](index.md)
