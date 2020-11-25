---
title: Metoda ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713772"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="64ed7-102">Metoda ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="64ed7-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="64ed7-103">Zwraca dostawcę symboli dla modułu z adresu podstawowego tego modułu.</span><span class="sxs-lookup"><span data-stu-id="64ed7-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ed7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="64ed7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ed7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="64ed7-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="64ed7-106">podczas Wartość [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="64ed7-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="64ed7-107">określoną Wskaźnik do adresu obiektu [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="64ed7-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64ed7-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="64ed7-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64ed7-109">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="64ed7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ed7-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="64ed7-110">Requirements</span></span>  

 <span data-ttu-id="64ed7-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ed7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ed7-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="64ed7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64ed7-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="64ed7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64ed7-114">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ed7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ed7-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="64ed7-115">See also</span></span>

- [<span data-ttu-id="64ed7-116">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="64ed7-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="64ed7-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="64ed7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
