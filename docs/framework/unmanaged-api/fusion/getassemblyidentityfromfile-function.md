---
title: GetAssemblyIdentityFromFile — Funkcja
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724484"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="bb563-102">GetAssemblyIdentityFromFile — Funkcja</span><span class="sxs-lookup"><span data-stu-id="bb563-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="bb563-103">Pobiera wskaźnik do `IUnknown` obiektu z określonym `IID` w zestawie w określonej ścieżce pliku.</span><span class="sxs-lookup"><span data-stu-id="bb563-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb563-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bb563-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb563-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="bb563-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="bb563-106">podczas Prawidłowa ścieżka do żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="bb563-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="bb563-107">podczas `IID` Interfejs do zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="bb563-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="bb563-108">określoną Zwrócony wskaźnik interfejsu.</span><span class="sxs-lookup"><span data-stu-id="bb563-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb563-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bb563-109">Requirements</span></span>  

 <span data-ttu-id="bb563-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb563-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb563-111">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bb563-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bb563-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb563-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb563-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bb563-113">See also</span></span>

- [<span data-ttu-id="bb563-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="bb563-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="bb563-115">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="bb563-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
