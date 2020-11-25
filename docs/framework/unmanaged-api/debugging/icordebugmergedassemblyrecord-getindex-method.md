---
title: 'ICorDebugMergedAssemblyRecord:: getIndex — Metoda'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 3056d22f5ddc1b11b79ee072aba68ce3ad40e8da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710639"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="f2899-102">ICorDebugMergedAssemblyRecord:: getIndex — Metoda</span><span class="sxs-lookup"><span data-stu-id="f2899-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>

<span data-ttu-id="f2899-103">Pobiera indeks prefiksu zestawu.</span><span class="sxs-lookup"><span data-stu-id="f2899-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2899-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2899-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2899-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f2899-105">Parameters</span></span>  

 `pIndex`  
 <span data-ttu-id="f2899-106">określoną Wskaźnik do indeksu prefiksu.</span><span class="sxs-lookup"><span data-stu-id="f2899-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2899-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f2899-107">Remarks</span></span>  

 <span data-ttu-id="f2899-108">Indeks prefiksu służy do zapobiegania kolizjom nazw w scalonych nazwach typów metadanych.</span><span class="sxs-lookup"><span data-stu-id="f2899-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2899-109">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2899-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2899-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f2899-110">Requirements</span></span>  

 <span data-ttu-id="f2899-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2899-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2899-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2899-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2899-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f2899-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2899-114">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2899-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2899-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2899-115">See also</span></span>

- [<span data-ttu-id="f2899-116">ICorDebugMergedAssemblyRecord, interfejs</span><span class="sxs-lookup"><span data-stu-id="f2899-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f2899-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f2899-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
