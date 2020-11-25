---
title: 'ICorDebugSymbolProvider:: GetCodeRange, Metoda'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: f61a98dbd5a65207a46e033d54f9d5f60adac201
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709131"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="16be7-102">ICorDebugSymbolProvider:: GetCodeRange, Metoda</span><span class="sxs-lookup"><span data-stu-id="16be7-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>

<span data-ttu-id="16be7-103">Pobiera adres początkowy i rozmiar metody z przyznanym adresem wirtualnym (RVA) w metodzie.</span><span class="sxs-lookup"><span data-stu-id="16be7-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16be7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="16be7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16be7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="16be7-105">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="16be7-106">podczas Względny adres wirtualny (RVA) w metodzie.</span><span class="sxs-lookup"><span data-stu-id="16be7-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="16be7-107">określoną Wskaźnik na adres początkowy metody.</span><span class="sxs-lookup"><span data-stu-id="16be7-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="16be7-108">Wskaźnik do rozmiaru kodu metody (liczba bajtów kodu metody).</span><span class="sxs-lookup"><span data-stu-id="16be7-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16be7-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="16be7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16be7-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="16be7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16be7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="16be7-111">Requirements</span></span>  

 <span data-ttu-id="16be7-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16be7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16be7-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="16be7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16be7-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="16be7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16be7-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16be7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be7-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="16be7-116">See also</span></span>

- [<span data-ttu-id="16be7-117">ICorDebugSymbolProvider, interfejs</span><span class="sxs-lookup"><span data-stu-id="16be7-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="16be7-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="16be7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
