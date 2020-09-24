---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4560c55cee5caf975e83ce9d4dc0b379ab905f8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156852"
---
# \<sessionTokenRequirement>

<span data-ttu-id="8d48d-101">Zapewnia konfigurację <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> klasy lub klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="8d48d-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="8d48d-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d48d-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d48d-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8d48d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8d48d-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8d48d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d48d-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8d48d-105">Attributes</span></span>  
  
|<span data-ttu-id="8d48d-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8d48d-106">Attribute</span></span>|<span data-ttu-id="8d48d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8d48d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d48d-108">cykl życia</span><span class="sxs-lookup"><span data-stu-id="8d48d-108">lifetime</span></span>|<span data-ttu-id="8d48d-109">Określa okres istnienia tokenów sesji.</span><span class="sxs-lookup"><span data-stu-id="8d48d-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d48d-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8d48d-110">Child Elements</span></span>  

 <span data-ttu-id="8d48d-111">Brak</span><span class="sxs-lookup"><span data-stu-id="8d48d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d48d-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8d48d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8d48d-113">Element</span><span class="sxs-lookup"><span data-stu-id="8d48d-113">Element</span></span>|<span data-ttu-id="8d48d-114">Opis</span><span class="sxs-lookup"><span data-stu-id="8d48d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="8d48d-115">Dodaje określony program obsługi tokenów zabezpieczających do kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="8d48d-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8d48d-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="8d48d-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
