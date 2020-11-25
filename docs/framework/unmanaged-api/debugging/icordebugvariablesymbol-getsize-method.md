---
title: 'ICorDebugVariableSymbol:: GetSize — metoda'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 1079351e75ec9c48a9657f514ee56e2e6a4b0920
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731374"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="1095d-102">ICorDebugVariableSymbol:: GetSize — metoda</span><span class="sxs-lookup"><span data-stu-id="1095d-102">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="1095d-103">Pobiera rozmiar zmiennej w bajtach.</span><span class="sxs-lookup"><span data-stu-id="1095d-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1095d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1095d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1095d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1095d-105">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="1095d-106">Wskaźnik do 32-bitowej liczby całkowitej bez znaku zawierającego rozmiar zmiennej.</span><span class="sxs-lookup"><span data-stu-id="1095d-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1095d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1095d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1095d-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1095d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1095d-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1095d-109">Requirements</span></span>  

 <span data-ttu-id="1095d-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1095d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1095d-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1095d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1095d-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1095d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1095d-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1095d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1095d-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1095d-114">See also</span></span>

- [<span data-ttu-id="1095d-115">ICorDebugVariableSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="1095d-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="1095d-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="1095d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
