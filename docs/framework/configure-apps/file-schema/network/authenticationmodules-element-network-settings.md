---
title: <authenticationModules>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 154a73a5fe3fa9e2b6b1c9e5c462b76bdc1ba640
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201749"
---
# <a name="authenticationmodules-element-network-settings"></a>\<authenticationModules>, element (ustawienia sieci)

Określa moduły używane do uwierzytelniania żądań sieci.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a>Składnia  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[add](add-element-for-authenticationmodules-network-settings.md)|Dodaje moduł uwierzytelniania do aplikacji.|  
|[Wyczyść](clear-element-for-authenticationmodules-network-settings.md)|Czyści wszystkie moduły uwierzytelniania z aplikacji.|  
|[usuwa](remove-element-for-authenticationmodules-network-settings.md)|Usuwa moduł uwierzytelniania z aplikacji.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Postaci**|**Opis**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.|  
  
## <a name="remarks"></a>Uwagi  

 `authenticationModule`Element określa moduły uwierzytelniania, które przeprowadzą proces uwierzytelniania z serwerem. Moduł uwierzytelniania musi implementować <xref:System.Net.IAuthenticationModule> interfejs.  
  
## <a name="configuration-files"></a>Pliki konfiguracji  

 Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład umożliwia włączenie modułu uwierzytelniania. Należy zastąpić wartości wersji i PublicKeyToken wartościami prawidłowymi dla określonego modułu.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [Schemat ustawień sieciowych](index.md)
