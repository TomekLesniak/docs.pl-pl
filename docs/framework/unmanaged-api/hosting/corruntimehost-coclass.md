---
title: CorRuntimeHost — Klasa coclass
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd4e675b4ba50b47146428d204c28cc943c23c69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688006"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="1ad34-102">CorRuntimeHost — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="1ad34-102">CorRuntimeHost Coclass</span></span>

<span data-ttu-id="1ad34-103">Udostępnia interfejsy do zarządzania aplikacjami, które są wykonywane przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="1ad34-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad34-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1ad34-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1ad34-105">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="1ad34-105">Interfaces</span></span>  
  
|<span data-ttu-id="1ad34-106">Interfejs</span><span class="sxs-lookup"><span data-stu-id="1ad34-106">Interface</span></span>|<span data-ttu-id="1ad34-107">Opis</span><span class="sxs-lookup"><span data-stu-id="1ad34-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1ad34-108">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1ad34-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="1ad34-109">Zapewnia metody konfigurowania środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="1ad34-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="1ad34-110">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1ad34-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="1ad34-111">Zapewnia metody umożliwiające uruchamianie hosta i zatrzymywanie jawnie środowiska uruchomieniowego języka wspólnego, tworzenie i Konfigurowanie domen aplikacji, dostęp do domeny domyślnej oraz wyliczanie wszystkich domen uruchomionych w procesie.</span><span class="sxs-lookup"><span data-stu-id="1ad34-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="1ad34-112">IDebuggerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1ad34-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="1ad34-113">Zapewnia metody uzyskiwania informacji o stanie usług debugowania.</span><span class="sxs-lookup"><span data-stu-id="1ad34-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="1ad34-114">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1ad34-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="1ad34-115">Zapewnia metody uzyskiwania informacji o systemie odzyskiwania pamięci i kontrolowania niektórych aspektów wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="1ad34-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="1ad34-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="1ad34-116">"IValidator"</span></span>|<span data-ttu-id="1ad34-117">Zapewnia metody weryfikacji przenośnych obrazów wykonywalnych i szczegółowe raportowanie błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="1ad34-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ad34-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1ad34-118">Requirements</span></span>  

 <span data-ttu-id="1ad34-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ad34-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad34-120">**Nagłówek:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="1ad34-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1ad34-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ad34-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ad34-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad34-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad34-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1ad34-123">See also</span></span>

- [<span data-ttu-id="1ad34-124">Współklasy hostingu</span><span class="sxs-lookup"><span data-stu-id="1ad34-124">Hosting Coclasses</span></span>](hosting-coclasses.md)
