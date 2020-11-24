---
title: ICLRAppDomainResourceMonitor — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 84c53f0666d0e04b898e28c1d8e146eab566ca1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674700"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>ICLRAppDomainResourceMonitor — Interfejs

Dostarcza metody, które sprawdzają użycie procesora i pamięci domeny aplikacji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCurrentAllocated, metoda](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Pobiera łączny rozmiar (w bajtach) wszystkich alokacji pamięci wykonanych przez domenę aplikacji od momentu utworzenia, bez odejmowania pamięci, która została zebrana jako elementy bezużyteczne.|  
|[GetCurrentSurvived, metoda](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Pobiera liczbę bajtów, które przeżyły ostatnią pełną, blokującą wyrzucanie elementów bezużytecznych i przywoływanych przez bieżącą domenę aplikacji.|  
|[GetCurrentCpuTime, metoda](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Pobiera łączny czas procesora, który był używany przez wszystkie wątki podczas wykonywania w bieżącej domenie aplikacji, od momentu utworzenia domeny aplikacji.|  
  
## <a name="remarks"></a>Uwagi  

 `ICLRAppDomainResourceMonitor`Interfejs udostępnia funkcje podobne do następujących właściwości zarządzanych:  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [\<appDomainResourceMonitoring> Postaci](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Monitorowanie zasobów domeny aplikacji](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
