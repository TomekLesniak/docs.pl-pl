---
title: Funkcja CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674167"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="4929b-102">Funkcja CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="4929b-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="4929b-103">Zwalnia zasoby przydzieloną dla struktury [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="4929b-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4929b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4929b-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4929b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4929b-105">Parameters</span></span>  

 `pTimestamperInfo`  
 <span data-ttu-id="4929b-106">[in. out] Informacje o sygnaturze czasowej do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="4929b-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="4929b-107">Zobacz strukturę [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="4929b-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4929b-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4929b-108">Return Value</span></span>  

 <span data-ttu-id="4929b-109">`S_OK` Jeśli funkcja się powiedzie.</span><span class="sxs-lookup"><span data-stu-id="4929b-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="4929b-110">W przeciwnym razie zwraca kod błędu.</span><span class="sxs-lookup"><span data-stu-id="4929b-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4929b-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4929b-111">See also</span></span>

- [<span data-ttu-id="4929b-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="4929b-112">Authenticode</span></span>](index.md)
