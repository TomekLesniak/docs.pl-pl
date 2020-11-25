---
title: IHostPolicyManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: 3c85bcbe8aee453b19217ebd1f48feea113e3bb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731224"
---
# <a name="ihostpolicymanager-interface"></a>IHostPolicyManager — Interfejs

Dostarcza metody, które powiadamiają hosta o akcjach wykonywanych przez środowisko uruchomieniowe języka wspólnego (CLR) w przypadku przerwań, limitów czasu lub niepowodzeń.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[OnDefaultAction, metoda](ihostpolicymanager-ondefaultaction-method.md)|Powiadamia hosta, że środowisko CLR ma wykonać akcję domyślną określoną przez wywołanie [ICLRPolicyManager:: SetDefaultAction —](iclrpolicymanager-setdefaultaction-method.md) w odpowiedzi na przerwanie lub <xref:System.AppDomain> zwolnienie wątku.|  
|[OnFailure, metoda](ihostpolicymanager-onfailure-method.md)|Powiadamia hosta, że środowisko CLR ma wykonać akcję określoną przez wywołanie [ICLRPolicyManager:: SetActionOnFailure —](iclrpolicymanager-setactiononfailure-method.md) w odpowiedzi na błąd alokacji zasobów lub odzyskania.|  
|[OnTimeout, metoda](ihostpolicymanager-ontimeout-method.md)|Powiadamia hosta, że środowisko CLR ma wykonać akcję określoną przez wywołanie [ICLRPolicyManager:: SetActionOnTimeout —](iclrpolicymanager-setactionontimeout-method.md) w odpowiedzi na limit czasu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [EClrFailure — Wyliczenie](eclrfailure-enumeration.md)
- [EClrOperation — Wyliczenie](eclroperation-enumeration.md)
- [EPolicyAction — Wyliczenie](epolicyaction-enumeration.md)
- [ICLRPolicyManager — Interfejs](iclrpolicymanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
