---
title: 'ICorDebugVariableSymbol:: GetName — Metoda'
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: aa3f335516f7fa22a77b786cd870f2a5064aeff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727630"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="5f208-102">ICorDebugVariableSymbol:: GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="5f208-102">ICorDebugVariableSymbol::GetName Method</span></span>

<span data-ttu-id="5f208-103">Pobiera nazwę zmiennej.</span><span class="sxs-lookup"><span data-stu-id="5f208-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f208-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5f208-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f208-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5f208-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="5f208-106">podczas Liczba znaków w `szName` buforze.</span><span class="sxs-lookup"><span data-stu-id="5f208-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5f208-107">określoną Wskaźnik do liczby znaków rzeczywiście zapisywana w `szName` buforze.</span><span class="sxs-lookup"><span data-stu-id="5f208-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="5f208-108">Wskaźnik do tablicy znaków, która zawiera nazwę zmiennej.</span><span class="sxs-lookup"><span data-stu-id="5f208-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f208-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5f208-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f208-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f208-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f208-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5f208-111">Requirements</span></span>  

 <span data-ttu-id="5f208-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f208-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f208-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5f208-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f208-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5f208-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f208-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f208-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f208-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5f208-116">See also</span></span>

- [<span data-ttu-id="5f208-117">ICorDebugVariableSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="5f208-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5f208-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5f208-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
