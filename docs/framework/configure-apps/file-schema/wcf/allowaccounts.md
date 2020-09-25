---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 3432d33c0cd65af03d2b1ac1302ca2c8ff3e0f43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201645"
---
# \<allowAccounts>

Zawiera kolekcję elementów konfiguracji, które określają konta użytkowników dla procesów, które obsługują usługi Windows Communication Foundation (WCF) i uzyskują dostęp do połączenia z usługą udostępniania.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|Dodaje konto użytkownika dla procesów, które obsługują usługi WCF i uzyskuje dostęp do połączenia z usługą udostępniania.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<net.pipe>](net-pipe.md) oraz [\<net.tcp>](net-tcp.md)|Określa ustawienia konfiguracji dla potoku sieci lub usług współużytkowania TCP.|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
