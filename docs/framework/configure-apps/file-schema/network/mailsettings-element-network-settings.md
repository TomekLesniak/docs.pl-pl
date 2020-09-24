---
title: <mailSettings>, element (ustawienia sieci)
description: <mailSettings>Element ustawienia sieci konfiguruje opcje wysyłania poczty w .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: a146874acc21f52507b37b1751c648792e23c8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158854"
---
# <a name="mailsettings-element-network-settings"></a>\<mailSettings>, element (ustawienia sieci)

Konfiguruje opcje wysyłania poczty.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a>Składnia  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|[\<smtp> — Element (Ustawienia sieci)](smtp-element-network-settings.md)|Konfiguruje opcje protokołu Simple Mail Transport.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[\<system.Net> — Element (Ustawienia sieci)](system-net-element-network-settings.md)|Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.|  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie określono odpowiednie parametry SMTP do wysyłania wiadomości e-mail przy użyciu domyślnych poświadczeń sieciowych.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.Mail.SmtpClient>
- [Schemat ustawień sieciowych](index.md)
