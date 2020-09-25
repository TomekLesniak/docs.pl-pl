---
title: <clear>, element dla bypasslist (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 96cef2dff3156e49a93be818230c83370dab5264
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185864"
---
# <a name="clear-element-for-bypasslist-network-settings"></a>\<clear>, element dla bypasslist (ustawienia sieci)

Czyści listę pomijania proxy.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Składnia  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Zawiera zestaw wyrażeń regularnych, które opisują adresy, które nie korzystają z serwera proxy.|  
  
## <a name="remarks"></a>Uwagi  

 `clear`Element czyści wszystkie wpisy z listy pomijania.  
  
## <a name="configuration-files"></a>Pliki konfiguracji  

 Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład czyści listę pomijania, a następnie dodaje dwa adresy do listy pomijania. Najpierw pomija serwer proxy dla wszystkich serwerów w domenie contoso.com; drugi pomija serwer proxy dla wszystkich serwerów, których adres IP rozpoczyna się od 192,168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schemat ustawień sieciowych](index.md)
