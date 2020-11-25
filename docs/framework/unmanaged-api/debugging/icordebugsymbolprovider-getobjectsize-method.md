---
title: 'ICorDebugSymbolProvider:: GetObjectSize —, Metoda'
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 4937ff1be7736f98be9efb9b01bdb322bf33e037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730811"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="bace5-102">ICorDebugSymbolProvider:: GetObjectSize —, Metoda</span><span class="sxs-lookup"><span data-stu-id="bace5-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="bace5-103">Zwraca rozmiar obiektu na podstawie jego podpisu elementu TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="bace5-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bace5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bace5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bace5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="bace5-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="bace5-106">podczas Liczba bajtów w sygnaturze elementu TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="bace5-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="bace5-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="bace5-107">typeSig</span></span>  
 <span data-ttu-id="bace5-108">podczas Sygnatura elementu TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="bace5-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="bace5-109">określoną Wskaźnik do rozmiaru obiektu.</span><span class="sxs-lookup"><span data-stu-id="bace5-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bace5-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bace5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bace5-111">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bace5-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bace5-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bace5-112">Requirements</span></span>  

 <span data-ttu-id="bace5-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bace5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bace5-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bace5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bace5-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bace5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bace5-116">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bace5-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bace5-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bace5-117">See also</span></span>

- [<span data-ttu-id="bace5-118">ICorDebugSymbolProvider, interfejs</span><span class="sxs-lookup"><span data-stu-id="bace5-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="bace5-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="bace5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
