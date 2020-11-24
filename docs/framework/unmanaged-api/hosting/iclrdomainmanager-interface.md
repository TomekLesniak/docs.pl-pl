---
title: ICLRDomainManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681174"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager — Interfejs

Umożliwia hostowi określenie Menedżera domeny aplikacji, który będzie używany do inicjowania domyślnej domeny aplikacji, oraz do określania właściwości inicjacji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[SetAppDomainManagerType — Metoda](iclrdomainmanager-setappdomainmanagertype-method.md)|Określa typ, który pochodzi od <xref:System.AppDomainManager?displayProperty=nameWithType> klasy, Menedżera domeny aplikacji, który będzie używany do inicjowania domyślnej domeny aplikacji.|  
|[SetPropertiesForDefaultAppDomain, metoda](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Ustawia właściwości, które zostaną użyte do zainicjowania domyślnej domeny aplikacji.|  
  
## <a name="remarks"></a>Uwagi  

 Aby uzyskać wystąpienie tego interfejsu, wywołaj metodę [ICLRControl:: GetCLRManager —](iclrcontrol-getclrmanager-method.md) z menedżerem typu IID `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
