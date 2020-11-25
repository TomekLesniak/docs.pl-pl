---
title: 'ICorDebugSymbolProvider:: GetAssemblyImageMetadata, Metoda'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 9644d1323660730d210bd0305c2785fce4174455
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709144"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="f4dc4-102">ICorDebugSymbolProvider:: GetAssemblyImageMetadata, Metoda</span><span class="sxs-lookup"><span data-stu-id="f4dc4-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>

<span data-ttu-id="f4dc4-103">Zwraca metadane z scalonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="f4dc4-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4dc4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f4dc4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4dc4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f4dc4-105">Parameters</span></span>  

 `ppMemoryBuffer`  
 <span data-ttu-id="f4dc4-106">określoną Wskaźnik do adresu obiektu [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) , który zawiera informacje o rozmiarze i adresie metadanych scalonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="f4dc4-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4dc4-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f4dc4-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4dc4-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f4dc4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4dc4-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f4dc4-109">Requirements</span></span>  

 <span data-ttu-id="f4dc4-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4dc4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4dc4-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f4dc4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4dc4-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f4dc4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4dc4-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4dc4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dc4-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f4dc4-114">See also</span></span>

- [<span data-ttu-id="f4dc4-115">ICorDebugSymbolProvider, interfejs</span><span class="sxs-lookup"><span data-stu-id="f4dc4-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f4dc4-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f4dc4-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
