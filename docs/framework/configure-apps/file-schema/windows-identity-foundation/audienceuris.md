---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: c9787d8e0d8d66494bbf2dbd0e24ff39178a4cde
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189906"
---
# \<audienceUris>

<span data-ttu-id="24acc-101">Określa zestaw identyfikatorów URI, które są akceptowalnymi identyfikatorami jednostki uzależnionej (RP).</span><span class="sxs-lookup"><span data-stu-id="24acc-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="24acc-102">Tokeny nie zostaną zaakceptowane, chyba że zostaną objęte zakresem jednego z dozwolonych identyfikatorów URI odbiorców.</span><span class="sxs-lookup"><span data-stu-id="24acc-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="24acc-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="24acc-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24acc-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="24acc-104">Attributes and Elements</span></span>  

 <span data-ttu-id="24acc-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="24acc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24acc-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="24acc-106">Attributes</span></span>  
  
|<span data-ttu-id="24acc-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="24acc-107">Attribute</span></span>|<span data-ttu-id="24acc-108">Opis</span><span class="sxs-lookup"><span data-stu-id="24acc-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24acc-109">tryb</span><span class="sxs-lookup"><span data-stu-id="24acc-109">mode</span></span>|<span data-ttu-id="24acc-110">Wartość określająca <xref:System.IdentityModel.Selectors.AudienceUriMode> , czy ograniczenie odbiorców ma być stosowane do tokenu przychodzącego.</span><span class="sxs-lookup"><span data-stu-id="24acc-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="24acc-111">Możliwe wartości to "always", "Never" i "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="24acc-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="24acc-112">Wartość domyślna to "zawsze".</span><span class="sxs-lookup"><span data-stu-id="24acc-112">The default is "Always".</span></span> <span data-ttu-id="24acc-113">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="24acc-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24acc-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="24acc-114">Child Elements</span></span>  
  
|<span data-ttu-id="24acc-115">Element</span><span class="sxs-lookup"><span data-stu-id="24acc-115">Element</span></span>|<span data-ttu-id="24acc-116">Opis</span><span class="sxs-lookup"><span data-stu-id="24acc-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="24acc-117">Dodaje identyfikator URI określony przez `value` atrybut do kolekcji audienceUris.</span><span class="sxs-lookup"><span data-stu-id="24acc-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="24acc-118">`value` Atrybut jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="24acc-118">The `value` attribute is required.</span></span> <span data-ttu-id="24acc-119">W identyfikatorze URI jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="24acc-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="24acc-120">Czyści kolekcję audienceUris.</span><span class="sxs-lookup"><span data-stu-id="24acc-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="24acc-121">Wszystkie identyfikatory są usuwane z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="24acc-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="24acc-122">Usuwa identyfikator URI określony przez `value` atrybut z kolekcji audienceUris.</span><span class="sxs-lookup"><span data-stu-id="24acc-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="24acc-123">`value` Atrybut jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="24acc-123">The `value` attribute is required.</span></span> <span data-ttu-id="24acc-124">W identyfikatorze URI jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="24acc-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24acc-125">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="24acc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="24acc-126">Element</span><span class="sxs-lookup"><span data-stu-id="24acc-126">Element</span></span>|<span data-ttu-id="24acc-127">Opis</span><span class="sxs-lookup"><span data-stu-id="24acc-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="24acc-128">Zapewnia konfigurację kolekcji programów obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="24acc-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24acc-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="24acc-129">Remarks</span></span>  

 <span data-ttu-id="24acc-130">Domyślnie kolekcja jest pusta; Użyj `<add>` `<clear>` elementów, i, `<remove>` Aby zmodyfikować kolekcję.</span><span class="sxs-lookup"><span data-stu-id="24acc-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="24acc-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>obiekty i używają wartości w kolekcji identyfikatorów URI odbiorców w celu skonfigurowania dozwolonych ograniczeń identyfikatorów URI odbiorców w <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> obiektach.</span><span class="sxs-lookup"><span data-stu-id="24acc-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="24acc-132">`<audienceUris>`Element jest reprezentowany przez <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> klasę.</span><span class="sxs-lookup"><span data-stu-id="24acc-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="24acc-133">Pojedynczy identyfikator URI dodany do kolekcji jest reprezentowany przez <xref:System.IdentityModel.Configuration.AudienceUriElement> klasę.</span><span class="sxs-lookup"><span data-stu-id="24acc-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24acc-134">Użycie `<audienceUris>` elementu jako elementu podrzędnego [\<identityConfiguration>](identityconfiguration.md) elementu jest przestarzałe, ale nadal jest ono obsługiwane w celu zapewnienia zgodności z poprzednimi wersjami.</span><span class="sxs-lookup"><span data-stu-id="24acc-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="24acc-135">Ustawienia w `<securityTokenHandlerConfiguration>` elemencie Przesłoń te elementy w `<identityConfiguration>` elemencie.</span><span class="sxs-lookup"><span data-stu-id="24acc-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24acc-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="24acc-136">Example</span></span>  

 <span data-ttu-id="24acc-137">Poniższy kod XML przedstawia sposób konfigurowania akceptowalnych identyfikatorów URI odbiorców dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24acc-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="24acc-138">Ten przykład umożliwia skonfigurowanie pojedynczego identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="24acc-138">This example configures a single URI.</span></span> <span data-ttu-id="24acc-139">Tokeny należące do zakresu dla tego identyfikatora URI zostaną zaakceptowane. wszystkie pozostałe zostaną odrzucone.</span><span class="sxs-lookup"><span data-stu-id="24acc-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
