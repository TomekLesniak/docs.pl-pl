---
title: <add> dla <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: cd4b9fd02eee2de1d0e8be185ffb69c0eae1cd58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181729"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="88248-102">\<add> dla \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="88248-102">\<add> of \<allowAccounts></span></span>

<span data-ttu-id="88248-103">Określa konto użytkownika dla procesów, które obsługują usługi WCF i ma dostęp do połączenia z usługą udostępniania.</span><span class="sxs-lookup"><span data-stu-id="88248-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="88248-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="88248-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88248-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="88248-105">Attributes and Elements</span></span>  

 <span data-ttu-id="88248-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="88248-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88248-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="88248-107">Attributes</span></span>  
  
|<span data-ttu-id="88248-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="88248-108">Attribute</span></span>|<span data-ttu-id="88248-109">Opis</span><span class="sxs-lookup"><span data-stu-id="88248-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88248-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="88248-110">securityIdentifier</span></span>|<span data-ttu-id="88248-111">Ciąg określający unikatowy identyfikator używany do identyfikowania konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="88248-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="88248-112">Wartości domyślne to LocalSystem, Administratorzy, NS, LS i IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="88248-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88248-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="88248-113">Child Elements</span></span>  

 <span data-ttu-id="88248-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="88248-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88248-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="88248-115">Parent Elements</span></span>  
  
|<span data-ttu-id="88248-116">Element</span><span class="sxs-lookup"><span data-stu-id="88248-116">Element</span></span>|<span data-ttu-id="88248-117">Opis</span><span class="sxs-lookup"><span data-stu-id="88248-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="88248-118">Kolekcja elementów konfiguracji, które zawierają atrybut służący `securityIdentifier` do określania kont użytkowników dla procesów, które obsługują usługi WCF i mają dostęp do połączenia z usługą udostępniania.</span><span class="sxs-lookup"><span data-stu-id="88248-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88248-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="88248-119">Example</span></span>  

 <span data-ttu-id="88248-120">Poniższy przykład konfiguracji dodaje pięć domyślnych identyfikatorów kont użytkowników do tej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="88248-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="88248-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="88248-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
