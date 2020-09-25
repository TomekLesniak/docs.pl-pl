---
title: <webRequestModules>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 9396ca393523dce5593531f332e5c07241987947
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187007"
---
# <a name="webrequestmodules-element-network-settings"></a>\<webRequestModules>, element (ustawienia sieci)

Określa moduły, które mają być używane do żądania informacji z hostów sieciowych.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|Dodaje niestandardowy moduł żądania sieci Web do aplikacji.|  
|[Wyczyść](clear-element-for-webrequestmodules-network-settings.md)|Usuwa wszystkie zarejestrowane moduły żądania sieci Web z aplikacji.|  
|[usuwa](remove-element-for-webrequestmodules-network-settings.md)|Usuwa niestandardowy moduł żądania sieci Web z aplikacji.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.|  
  
## <a name="remarks"></a>Uwagi  

 `webRequestModules`Element rejestruje elementy podrzędne <xref:System.Net.WebRequest> klasy do obsługi żądań informacji do hostów sieciowych. Moduły żądania sieci Web muszą implementować <xref:System.Net.IWebRequestCreate> interfejs.  
  
 .NET Framework obejmuje moduły żądania sieci Web dla identyfikatorów URI zaczynających się od `http://` , `https://` i `file://` . Moduły domyślne można zastąpić tylko przez zarejestrowanie modułu niestandardowego w pliku konfiguracji.  
  
## <a name="configuration-files"></a>Pliki konfiguracji  

 Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład rejestruje domyślny moduł HTTP. Należy zastąpić wartości wersji i PublicKeyToken wartościami prawidłowymi dla określonego modułu.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Schemat ustawień sieciowych](index.md)
