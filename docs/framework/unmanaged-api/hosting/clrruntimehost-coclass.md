---
title: CLRRuntimeHost — Klasa coclass
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: 7c77cb2e89cb8fd87bf219780b9460649de19c9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731771"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="caa25-102">CLRRuntimeHost — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="caa25-102">CLRRuntimeHost Coclass</span></span>

<span data-ttu-id="caa25-103">Udostępnia interfejsy umożliwiające zarządzanie wykonywaniem kodu przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="caa25-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa25-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="caa25-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="caa25-105">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="caa25-105">Interfaces</span></span>  
  
|<span data-ttu-id="caa25-106">Interfejs</span><span class="sxs-lookup"><span data-stu-id="caa25-106">Interface</span></span>|<span data-ttu-id="caa25-107">Opis</span><span class="sxs-lookup"><span data-stu-id="caa25-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="caa25-108">ICLRRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="caa25-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="caa25-109">Zapewnia metody kontrolowania wykonywania aplikacji przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="caa25-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="caa25-110">ICLRValidator — Interfejs</span><span class="sxs-lookup"><span data-stu-id="caa25-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="caa25-111">Zapewnia metody weryfikacji przenośnych obrazów wykonywalnych i szczegółowe raportowanie błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="caa25-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="caa25-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="caa25-112">Requirements</span></span>  

 <span data-ttu-id="caa25-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa25-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa25-114">**Nagłówek:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="caa25-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="caa25-115">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caa25-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caa25-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa25-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="caa25-117">See also</span></span>

- [<span data-ttu-id="caa25-118">Współklasy hostingu</span><span class="sxs-lookup"><span data-stu-id="caa25-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
