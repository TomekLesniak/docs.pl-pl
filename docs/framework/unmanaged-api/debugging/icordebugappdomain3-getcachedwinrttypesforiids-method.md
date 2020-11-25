---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
ms.openlocfilehash: 2aff86fb63b87869ed13028bd7344afe11363f51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723184"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="cecb1-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs — Metoda</span><span class="sxs-lookup"><span data-stu-id="cecb1-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>

<span data-ttu-id="cecb1-103">Pobiera moduł wyliczający dla buforowanych środowisko wykonawcze systemu Windows typów w domenie aplikacji w oparciu o ich identyfikatory interfejsów.</span><span class="sxs-lookup"><span data-stu-id="cecb1-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecb1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cecb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cecb1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cecb1-105">Parameters</span></span>  

 `cReqTypes`  
 <span data-ttu-id="cecb1-106">podczas Liczba wymaganych typów.</span><span class="sxs-lookup"><span data-stu-id="cecb1-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="cecb1-107">podczas Wskaźnik do tablicy zawierającej identyfikatory interfejsów odpowiadające zarządzanym reprezentacjom typów środowisko wykonawcze systemu Windows do pobrania.</span><span class="sxs-lookup"><span data-stu-id="cecb1-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="cecb1-108">określoną Wskaźnik do adresu obiektu interfejsu "ICorDebugTypeEnum", który umożliwia Wyliczenie buforowanych reprezentacji typów środowisko wykonawcze systemu Windows pobranych, opartych na identyfikatorach interfejsu w `iidsToResolve` .</span><span class="sxs-lookup"><span data-stu-id="cecb1-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cecb1-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cecb1-109">Remarks</span></span>  

 <span data-ttu-id="cecb1-110">Jeśli metoda nie może pobrać informacji o określonym identyfikatorze interfejsu, odpowiadający wpis w kolekcji "ICorDebugTypeEnum" będzie miał typ `ELEMENT_TYPE_END` dla błędów spowodowany problemami z pobieraniem danych lub `ELEMENT_TYPE_VOID` nieznanymi identyfikatorami interfejsów.</span><span class="sxs-lookup"><span data-stu-id="cecb1-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cecb1-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cecb1-111">Requirements</span></span>  

 <span data-ttu-id="cecb1-112">**Platformy:** środowisko wykonawcze systemu Windows</span><span class="sxs-lookup"><span data-stu-id="cecb1-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="cecb1-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="cecb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cecb1-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cecb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cecb1-115">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cecb1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecb1-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cecb1-116">See also</span></span>

- [<span data-ttu-id="cecb1-117">ICorDebugAppDomain3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cecb1-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
