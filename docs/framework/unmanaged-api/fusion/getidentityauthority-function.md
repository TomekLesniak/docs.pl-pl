---
title: GetIdentityAuthority — Funkcja
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: e9631211993afbfe968c7122828251746f15c3f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732131"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="cc793-102">GetIdentityAuthority — Funkcja</span><span class="sxs-lookup"><span data-stu-id="cc793-102">GetIdentityAuthority Function</span></span>

<span data-ttu-id="cc793-103">Pobiera wskaźnik do wystąpienia [IIdentityAuthority —](iidentityauthority-interface.md) , które zarządza kluczami obiektów kodu.</span><span class="sxs-lookup"><span data-stu-id="cc793-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc793-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cc793-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc793-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cc793-105">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="cc793-106">określoną Zwrócony `IIdentityAuthority` wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="cc793-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc793-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cc793-107">Requirements</span></span>  

 <span data-ttu-id="cc793-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc793-109">**Nagłówek:** Izolacja. h</span><span class="sxs-lookup"><span data-stu-id="cc793-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="cc793-110">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc793-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc793-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cc793-111">See also</span></span>

- [<span data-ttu-id="cc793-112">IIdentityAuthority — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cc793-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="cc793-113">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="cc793-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
