---
title: EInitializeNewDomainFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724328"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags — Wyliczenie

Umożliwia hostowi zapewnienie środowiska uruchomieniowego z informacjami o inicjalizacji domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Brak flag.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informuje środowisko uruchomieniowe języka wspólnego (CLR), że host nie wprowadzi zmian w stanie zabezpieczeń domeny aplikacji w <xref:System.AppDomainManager.InitializeNewDomain%2A> metodzie.|  
  
## <a name="remarks"></a>Uwagi  

 Metoda [ICLRDomainManager:: SetAppDomainManagerType —](iclrdomainmanager-setappdomainmanagertype-method.md) przyjmuje parametr typu `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Wyliczenia](hosting-enumerations.md)
- [SetAppDomainManagerType — Metoda](iclrdomainmanager-setappdomainmanagertype-method.md)
