---
title: 'ICorDebugSymbolProvider:: GetMergedAssemblyRecords, Metoda'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 10bbcf2e6a536eeb4ab8141c10c177a53faa1c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730880"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="b3f21-102">ICorDebugSymbolProvider:: GetMergedAssemblyRecords, Metoda</span><span class="sxs-lookup"><span data-stu-id="b3f21-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>

<span data-ttu-id="b3f21-103">Pobiera rekordy symboli dla wszystkich scalonych zestawów.</span><span class="sxs-lookup"><span data-stu-id="b3f21-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f21-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b3f21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f21-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b3f21-105">Parameters</span></span>  

 `cRequestedRecords`  
 <span data-ttu-id="b3f21-106">podczas Liczba żądanych rekordów symboli.</span><span class="sxs-lookup"><span data-stu-id="b3f21-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="b3f21-107">określoną Wskaźnik do liczby rekordów symboli pobranych przez metodę.</span><span class="sxs-lookup"><span data-stu-id="b3f21-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="b3f21-108">Wskaźnik do tablicy obiektów [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b3f21-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3f21-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b3f21-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3f21-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b3f21-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f21-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b3f21-111">Requirements</span></span>  

 <span data-ttu-id="b3f21-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f21-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f21-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b3f21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3f21-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b3f21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3f21-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f21-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f21-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b3f21-116">See also</span></span>

- [<span data-ttu-id="b3f21-117">ICorDebugSymbolProvider, interfejs</span><span class="sxs-lookup"><span data-stu-id="b3f21-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b3f21-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="b3f21-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
