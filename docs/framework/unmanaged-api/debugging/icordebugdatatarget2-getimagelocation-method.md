---
title: Metoda ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: c909b46a9bb70d23d1cd3a769ac24fcf58479308
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713798"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="fdae7-102">Metoda ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="fdae7-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>

<span data-ttu-id="fdae7-103">Zwraca ścieżkę modułu z adresu podstawowego modułu.</span><span class="sxs-lookup"><span data-stu-id="fdae7-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdae7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fdae7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdae7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fdae7-105">Parameters</span></span>  

 `baseAddress`  
 <span data-ttu-id="fdae7-106">podczas Wartość [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="fdae7-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fdae7-107">podczas Liczba znaków w buforze, która ma otrzymać ścieżkę modułu.</span><span class="sxs-lookup"><span data-stu-id="fdae7-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fdae7-108">określoną Wskaźnik do liczby znaków zapisanych w `szName` buforze.</span><span class="sxs-lookup"><span data-stu-id="fdae7-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="fdae7-109">określoną Ścieżka modułu.</span><span class="sxs-lookup"><span data-stu-id="fdae7-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdae7-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fdae7-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdae7-111">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fdae7-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdae7-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fdae7-112">Requirements</span></span>  

 <span data-ttu-id="fdae7-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdae7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdae7-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fdae7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdae7-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fdae7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdae7-116">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdae7-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdae7-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fdae7-117">See also</span></span>

- [<span data-ttu-id="fdae7-118">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="fdae7-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="fdae7-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="fdae7-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
