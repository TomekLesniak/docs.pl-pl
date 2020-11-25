---
title: CloseEnum — Metoda
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
ms.openlocfilehash: 59b1ec3f9ca382ef13680e3aad4d0c0c0e175f1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716970"
---
# <a name="closeenum-method"></a><span data-ttu-id="cd866-102">CloseEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="cd866-102">CloseEnum Method</span></span>

<span data-ttu-id="cd866-103">Zamyka wskazane Wyliczenie i zwalnia skojarzone zasoby.</span><span class="sxs-lookup"><span data-stu-id="cd866-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd866-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd866-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd866-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cd866-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="cd866-106">Dojście wyliczenia do zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="cd866-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd866-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cd866-107">Return Value</span></span>  

 <span data-ttu-id="cd866-108">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cd866-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd866-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cd866-109">Requirements</span></span>  

 <span data-ttu-id="cd866-110">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="cd866-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd866-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cd866-111">See also</span></span>

- [<span data-ttu-id="cd866-112">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cd866-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cd866-113">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cd866-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cd866-114">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="cd866-114">ALink API</span></span>](index.md)
