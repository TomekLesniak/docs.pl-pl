---
title: IActionOnCLREvent — Interfejs
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 8ca4bb1fe35451f95f752a4e71f5f0b541b55e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721780"
---
# <a name="iactiononclrevent-interface"></a>IActionOnCLREvent — Interfejs

Udostępnia metodę [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) , która wykonuje wywołania zwrotne dla zdarzeń, które zostały zarejestrowane przy użyciu wywołania metody [ICLROnEventManager:: RegisterActionOnEvent —](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[OnEvent, metoda](iactiononclrevent-onevent-method.md)|Wykonuje wywołanie zwrotne dla zarejestrowanego zdarzenia.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [EClrEvent — Wyliczenie](eclrevent-enumeration.md)
- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [ICLROnEventManager — Interfejs](iclroneventmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
