---
title: <settings>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167278"
---
# <a name="settings-element-network-settings"></a>\<settings>, element (ustawienia sieci)

Konfiguruje podstawowe opcje sieci dla <xref:System.Net?displayProperty=nameWithType> przestrzeni nazw.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a>Składnia  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[Odbiornika HttpListener](httplistener-element-network-settings.md)|Dostosowuje parametry używane przez <xref:System.Net.HttpListener> klasę.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Dostosowuje parametry żądania sieci Web.|  
|[If](ipv6-element-network-settings.md)|Włącza obsługę protokołu internetowego w wersji 6 (IPv6).|  
|[\<performanceCounter> — Element (Ustawienia sieci)](performancecounter-element-network-settings.md)|Włącza liczniki wydajności sieci.|  
|[ServicePointManager](servicepointmanager-element-network-settings.md)|Konfiguruje połączenia z zasobami sieciowymi.|  
|[używając](socket-element-network-settings.md)|Określa, czy operacje gniazda używają portów zakończenia.|  
|[\<webProxyScript> — Element (Ustawienia sieci)](webproxyscript-element-network-settings.md)|Konfiguruje charakterystyki skryptu służącego do odnajdywania serwerów proxy sieci Web.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="configuration-files"></a>Pliki konfiguracji  

 Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net?displayProperty=nameWithType>
- [Schemat ustawień sieciowych](index.md)
