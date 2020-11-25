---
title: ComCallUnmarshal — Klasa coclass
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731725"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="b06ed-102">ComCallUnmarshal — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="b06ed-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="b06ed-103">Udostępnia interfejsy służące do zarządzania kierowaniem wskaźników interfejsu.</span><span class="sxs-lookup"><span data-stu-id="b06ed-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06ed-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b06ed-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b06ed-105">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="b06ed-105">Interfaces</span></span>  
  
|<span data-ttu-id="b06ed-106">Interfejs</span><span class="sxs-lookup"><span data-stu-id="b06ed-106">Interface</span></span>|<span data-ttu-id="b06ed-107">Opis</span><span class="sxs-lookup"><span data-stu-id="b06ed-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="b06ed-108">Zapewnia metody tworzenia, inicjowania i zarządzania serwerem proxy w procesie klienta.</span><span class="sxs-lookup"><span data-stu-id="b06ed-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b06ed-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b06ed-109">Requirements</span></span>  

 <span data-ttu-id="b06ed-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b06ed-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06ed-111">**Nagłówek:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="b06ed-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b06ed-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b06ed-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b06ed-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b06ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06ed-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b06ed-114">See also</span></span>

- [<span data-ttu-id="b06ed-115">Współklasy hostingu</span><span class="sxs-lookup"><span data-stu-id="b06ed-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
