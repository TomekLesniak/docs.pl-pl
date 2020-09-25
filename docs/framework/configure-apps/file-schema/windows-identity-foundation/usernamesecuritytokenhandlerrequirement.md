---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: a49b41c04c8f184188b62e04c3b232bd33752fca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185525"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="a3eaf-101">Zapewnia konfigurację <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> klasy lub klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="a3eaf-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="a3eaf-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3eaf-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3eaf-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a3eaf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a3eaf-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a3eaf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3eaf-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a3eaf-105">Attributes</span></span>  
  
|<span data-ttu-id="a3eaf-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a3eaf-106">Attribute</span></span>|<span data-ttu-id="a3eaf-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a3eaf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3eaf-108">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="a3eaf-108">membershipProviderName</span></span>|<span data-ttu-id="a3eaf-109">Określa <xref:System.Web.Security.MembershipProvider> , który ma być używany przez program obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="a3eaf-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3eaf-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a3eaf-110">Child Elements</span></span>  

 <span data-ttu-id="a3eaf-111">Brak</span><span class="sxs-lookup"><span data-stu-id="a3eaf-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3eaf-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a3eaf-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a3eaf-113">Element</span><span class="sxs-lookup"><span data-stu-id="a3eaf-113">Element</span></span>|<span data-ttu-id="a3eaf-114">Opis</span><span class="sxs-lookup"><span data-stu-id="a3eaf-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="a3eaf-115">Dodaje określony program obsługi tokenów zabezpieczających do kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="a3eaf-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3eaf-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3eaf-116">Remarks</span></span>  

 <span data-ttu-id="a3eaf-117">`<userNameSecurityTokenHandlerRequirement>`Element ustawia właściwość, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> gdy <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> obiekt jest inicjowany z konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a3eaf-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3eaf-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3eaf-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
