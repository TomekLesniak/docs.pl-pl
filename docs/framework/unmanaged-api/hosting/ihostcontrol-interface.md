---
title: IHostControl — Interfejs
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680664"
---
# <a name="ihostcontrol-interface"></a>IHostControl — Interfejs

Zapewnia metody konfigurowania ładowania zestawów i określania interfejsów hostingu obsługiwanych przez hosta.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetHostManager, metoda](ihostcontrol-gethostmanager-method.md)|Pobiera wskaźnik interfejsu do implementacji hosta interfejsu z określonym `IID` .|  
|[SetAppDomainManager, metoda](ihostcontrol-setappdomainmanager-method.md)|Powiadamia hosta o utworzeniu domeny aplikacji.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost — Interfejs](iclrruntimehost-interface.md)
- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
