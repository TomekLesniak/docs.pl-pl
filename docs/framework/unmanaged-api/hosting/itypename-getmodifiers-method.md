---
title: ITypeName::GetModifiers — Metoda
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 64751032c017473ffd82248b310b14c087f74129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727838"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="38136-102">ITypeName::GetModifiers — Metoda</span><span class="sxs-lookup"><span data-stu-id="38136-102">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="38136-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="38136-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38136-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="38136-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="38136-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="38136-105">Requirements</span></span>  

 <span data-ttu-id="38136-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38136-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38136-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="38136-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38136-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38136-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38136-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38136-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38136-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="38136-110">See also</span></span>

- [<span data-ttu-id="38136-111">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="38136-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
