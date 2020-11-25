---
title: ICorDebugComObjectValue::GetCachedInterfacePointers — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: c3120a0dd859f581e6356fc260043cb83250ae9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724835"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="4bd0c-102">ICorDebugComObjectValue::GetCachedInterfacePointers — Metoda</span><span class="sxs-lookup"><span data-stu-id="4bd0c-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>

<span data-ttu-id="4bd0c-103">Pobiera pierwotne wskaźniki interfejsu w pamięci podręcznej dla bieżącej otoki (RCW) w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd0c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4bd0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd0c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4bd0c-105">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="4bd0c-106">podczas Wartość wskazująca, czy metoda zwróci tylko środowisko wykonawcze systemu Windows interfejsy ( `IInspectable` interfejsy) czy wszystkie interfejsy com, które są buforowane przez otokę wywoływaną przez środowisko uruchomieniowe (otoka).</span><span class="sxs-lookup"><span data-stu-id="4bd0c-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="4bd0c-107">podczas Liczba obiektów, których adresy mają zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4bd0c-108">określoną Wskaźnik do liczby `CORDB_ADDRESS` wartości faktycznie zwracanych w `ptrs` .</span><span class="sxs-lookup"><span data-stu-id="4bd0c-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="4bd0c-109">Wskaźnik na adres początkowy tablicy `CORDB_ADDRESS` wartości zawierającej adresy buforowanych obiektów interfejsu.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bd0c-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4bd0c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd0c-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4bd0c-111">Requirements</span></span>  

 <span data-ttu-id="4bd0c-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd0c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd0c-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4bd0c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bd0c-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4bd0c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd0c-115">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd0c-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4bd0c-116">See also</span></span>

- [<span data-ttu-id="4bd0c-117">ICorDebugComObjectValue — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4bd0c-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="4bd0c-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="4bd0c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
