---
title: 'ICorDebugInstanceFieldSymbol:: GetName — Metoda'
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: e466a62761cc6dd1f1fc0a54f05d54f85c190d07
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724939"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="0ae46-102">ICorDebugInstanceFieldSymbol:: GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="0ae46-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="0ae46-103">Pobiera nazwę pola wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0ae46-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae46-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0ae46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae46-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0ae46-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0ae46-106">podczas Liczba znaków w `szName` buforze.</span><span class="sxs-lookup"><span data-stu-id="0ae46-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0ae46-107">określoną Wskaźnik do liczby znaków rzeczywiście zapisywana w `szName` buforze.</span><span class="sxs-lookup"><span data-stu-id="0ae46-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ae46-108">określoną Tablica znaków przechowująca zwróconą nazwę.</span><span class="sxs-lookup"><span data-stu-id="0ae46-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ae46-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ae46-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ae46-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ae46-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae46-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0ae46-111">Requirements</span></span>  

 <span data-ttu-id="0ae46-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae46-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae46-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0ae46-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ae46-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0ae46-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ae46-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae46-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae46-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0ae46-116">See also</span></span>

- [<span data-ttu-id="0ae46-117">ICorDebugInstanceFieldSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="0ae46-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="0ae46-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="0ae46-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
