---
title: ICLRControl — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728345"
---
# <a name="iclrcontrol-interface"></a>ICLRControl — Interfejs

Dostarcza metody, które umożliwiają hostowi uzyskanie odwołań do i Konfigurowanie aspektów środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCLRManager, metoda](iclrcontrol-getclrmanager-method.md)|Pobiera wskaźnik interfejsu do wystąpienia dowolnego typu Menedżera, którego host może użyć do skonfigurowania środowiska CLR.|  
|[SetAppDomainManagerType — Metoda](iclrcontrol-setappdomainmanagertype-method.md)|Ustawia typ pochodzący od <xref:System.AppDomainManager> typu dla menedżerów domeny aplikacji.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyIdentityManager — Interfejs](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager — Interfejs](iclrdebugmanager-interface.md)
- [ICLRGCManager — Interfejs](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager — Interfejs](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager — Interfejs](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager — Interfejs](iclroneventmanager-interface.md)
- [ICLRPolicyManager — Interfejs](iclrpolicymanager-interface.md)
- [IHostControl — Interfejs](ihostcontrol-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
