---
title: Metoda ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713824"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="2e846-102">Metoda ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="2e846-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="2e846-103">Zwraca adres podstawowy i rozmiar modułu z adresu w tym module.</span><span class="sxs-lookup"><span data-stu-id="2e846-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e846-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2e846-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e846-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2e846-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="2e846-106">Wartość [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje adres w module.</span><span class="sxs-lookup"><span data-stu-id="2e846-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="2e846-107">określoną Wartość [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="2e846-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="2e846-108">Wskaźnik do rozmiaru modułu.</span><span class="sxs-lookup"><span data-stu-id="2e846-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e846-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2e846-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e846-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2e846-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e846-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2e846-111">Requirements</span></span>  

 <span data-ttu-id="2e846-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e846-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e846-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2e846-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e846-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2e846-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e846-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e846-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e846-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2e846-116">See also</span></span>

- [<span data-ttu-id="2e846-117">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2e846-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2e846-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="2e846-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
