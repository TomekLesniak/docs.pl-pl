---
title: ICorRuntimeHost::GetConfiguration — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720649"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="3fa0b-102">ICorRuntimeHost::GetConfiguration — Metoda</span><span class="sxs-lookup"><span data-stu-id="3fa0b-102">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="3fa0b-103">Pobiera obiekt, który umożliwia hostowi określenie konfiguracji wywołania zwrotnego środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="3fa0b-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa0b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3fa0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fa0b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3fa0b-105">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="3fa0b-106">określoną Wskaźnik do adresu obiektu [ICorConfiguration](icorconfiguration-interface.md) , który może służyć do konfigurowania środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="3fa0b-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fa0b-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3fa0b-107">Remarks</span></span>  

 <span data-ttu-id="3fa0b-108">Środowisko CLR musi być skonfigurowane przed jego inicjalizacją; w przeciwnym razie `GetConfiguration` Metoda zwraca wynik HRESULT wskazujący błąd.</span><span class="sxs-lookup"><span data-stu-id="3fa0b-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fa0b-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3fa0b-109">Requirements</span></span>  

 <span data-ttu-id="3fa0b-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa0b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa0b-111">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3fa0b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fa0b-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fa0b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fa0b-113">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="3fa0b-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa0b-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3fa0b-114">See also</span></span>

- [<span data-ttu-id="3fa0b-115">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3fa0b-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
