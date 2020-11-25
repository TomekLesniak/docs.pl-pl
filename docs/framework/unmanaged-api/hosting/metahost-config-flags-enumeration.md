---
title: METAHOST_CONFIG_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
ms.openlocfilehash: 01e55659bf2a348ec763f51112cbdcd706f27c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730009"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="03606-102">METAHOST_CONFIG_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="03606-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>

<span data-ttu-id="03606-103">Opisuje możliwe flagi zwracane w `pdwConfigFlags` parametrze metody [ICLRMetaHostPolicy:: GetRequestedRuntime —](iclrmetahostpolicy-getrequestedruntime-method.md) , wskazującą obecność i ustawienie `useLegacyV2RuntimeActivationPolicy` atrybutu w [ \<startup> elemencie](../../configure-apps/file-schema/startup/startup-element.md) pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="03606-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03606-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="03606-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="03606-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="03606-105">Members</span></span>  
  
|<span data-ttu-id="03606-106">Członek</span><span class="sxs-lookup"><span data-stu-id="03606-106">Member</span></span>|<span data-ttu-id="03606-107">Opis</span><span class="sxs-lookup"><span data-stu-id="03606-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="03606-108">`useLegacyV2RuntimeActivationPolicy`Atrybut nie był obecny w [ \<startup> elemencie](../../configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="03606-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="03606-109">`useLegacyV2RuntimeActivationPolicy`Atrybut był obecny i ma ustawioną wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="03606-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="03606-110">`useLegacyV2RuntimeActivationPolicy`Atrybut był obecny i ma ustawioną wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="03606-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="03606-111">Zastosuj tę maskę do wartości zwróconej w `pdwConfigFlags` celu uzyskania wartości odpowiednich dla `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="03606-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03606-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="03606-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03606-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="03606-113">Requirements</span></span>  

 <span data-ttu-id="03606-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03606-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03606-115">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="03606-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="03606-116">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03606-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03606-117">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03606-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03606-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="03606-118">See also</span></span>

- [<span data-ttu-id="03606-119">Hosting — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="03606-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="03606-120">GetRequestedRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="03606-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="03606-121">\<startup> Postaci</span><span class="sxs-lookup"><span data-stu-id="03606-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
