---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: c4ba7b6f2a9b9092c5f24d424c6de2b0f510ac88
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165003"
---
# \<remove>

<span data-ttu-id="f66bc-101">Usuwa określony program obsługi tokenów zabezpieczających z kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="f66bc-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="f66bc-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="f66bc-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f66bc-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f66bc-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f66bc-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f66bc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f66bc-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f66bc-105">Attributes</span></span>  
  
|<span data-ttu-id="f66bc-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f66bc-106">Attribute</span></span>|<span data-ttu-id="f66bc-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f66bc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f66bc-108">typ</span><span class="sxs-lookup"><span data-stu-id="f66bc-108">type</span></span>|<span data-ttu-id="f66bc-109">Nazwa typu CLR programu obsługi tokenów, który ma zostać usunięty.</span><span class="sxs-lookup"><span data-stu-id="f66bc-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="f66bc-110">Aby uzyskać więcej informacji na temat sposobu określania `type` atrybutu, zobacz [odwołania do typów niestandardowych](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="f66bc-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="f66bc-111">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="f66bc-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f66bc-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f66bc-112">Child Elements</span></span>  

 <span data-ttu-id="f66bc-113">Brak</span><span class="sxs-lookup"><span data-stu-id="f66bc-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f66bc-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f66bc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f66bc-115">Element</span><span class="sxs-lookup"><span data-stu-id="f66bc-115">Element</span></span>|<span data-ttu-id="f66bc-116">Opis</span><span class="sxs-lookup"><span data-stu-id="f66bc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="f66bc-117">Określa kolekcję programów obsługi tokenów zabezpieczających, które są zarejestrowane w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="f66bc-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f66bc-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="f66bc-118">Example</span></span>  

 <span data-ttu-id="f66bc-119">Poniższy kod XML pokazuje użycie `<add>` elementów i, `<remove>` Aby zastąpić domyślną procedurę obsługi tokena sesji za pomocą procedury obsługi niestandardowego tokenu sesji.</span><span class="sxs-lookup"><span data-stu-id="f66bc-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="f66bc-120">KOD XML jest pobierany z `ClaimsAwareWebFarm` przykładu.</span><span class="sxs-lookup"><span data-stu-id="f66bc-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
