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

<span data-ttu-id="dba87-101">Zawiera kolekcję elementów konfiguracji, które określają konta użytkowników dla procesów, które obsługują usługi Windows Communication Foundation (WCF) i uzyskują dostęp do połączenia z usługą udostępniania.</span><span class="sxs-lookup"><span data-stu-id="dba87-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="dba87-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="dba87-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dba87-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="dba87-103">Attributes and Elements</span></span>  

 <span data-ttu-id="dba87-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="dba87-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dba87-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="dba87-105">Attributes</span></span>  

 <span data-ttu-id="dba87-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="dba87-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dba87-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="dba87-107">Child Elements</span></span>  
  
|<span data-ttu-id="dba87-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="dba87-108">Attribute</span></span>|<span data-ttu-id="dba87-109">Opis</span><span class="sxs-lookup"><span data-stu-id="dba87-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="dba87-110">Dodaje konto użytkownika dla procesów, które obsługują usługi WCF i uzyskuje dostęp do połączenia z usługą udostępniania.</span><span class="sxs-lookup"><span data-stu-id="dba87-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dba87-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="dba87-111">Parent Elements</span></span>  
  
|<span data-ttu-id="dba87-112">Element</span><span class="sxs-lookup"><span data-stu-id="dba87-112">Element</span></span>|<span data-ttu-id="dba87-113">Opis</span><span class="sxs-lookup"><span data-stu-id="dba87-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dba87-114">[\<net.pipe>](net-pipe.md) oraz [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="dba87-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="dba87-115">Określa ustawienia konfiguracji dla potoku sieci lub usług współużytkowania TCP.</span><span class="sxs-lookup"><span data-stu-id="dba87-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dba87-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dba87-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
