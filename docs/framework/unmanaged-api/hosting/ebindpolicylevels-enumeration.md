---
title: EBindPolicyLevels — Wyliczenie
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726850"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels — Wyliczenie

Zapewnia flagi do określania poziomu, na którym mają być stosowane lub zmodyfikowane zasady zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Określa, że zasady mają być stosowane na poziomie administratora.|  
|`ePolicyLevelApp`|Określa, że zasady mają być stosowane na poziomie aplikacji.|  
|`ePolicyLevelHost`|Określa, że zasady mają być stosowane na poziomie hosta.|  
|`ePolicyLevelNone`|Określa brak flag poziomu zasad.|  
|`ePolicyLevelPublisher`|Określa, że zasady mają być stosowane na poziomie wydawcy.|  
|`ePolicyLevelRetargetable`|Określa, że zasady powinny być stosowane na poziomach zmiennych.|  
|`ePolicyPortability`|Określa, że zasady powinny obsługiwać przenośność między implementacjami zestawu .NET Framework. Zobacz [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) element pliku konfiguracji.|  
|`ePolicyUnifiedToCLR`|Określa, że zasady powinny być ujednolicone dla tego środowiska uruchomieniowego języka wspólnego (CLR).|  
  
## <a name="remarks"></a>Uwagi  

 To wyliczenie jest przesyłane do metod interfejsu [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) , aby określić zmiany zasad aplikacji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyIdentityManager — Interfejs](iclrassemblyidentitymanager-interface.md)
- [Hosting — Wyliczenia](hosting-enumerations.md)
