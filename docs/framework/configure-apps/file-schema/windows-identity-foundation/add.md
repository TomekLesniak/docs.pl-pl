---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 7c2b6bdc62da63905d7ff33a9984808e7b7d114f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544543"
---
# \<add>
<span data-ttu-id="77fc4-101">Dodaje określony program obsługi tokenów zabezpieczających do kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="77fc4-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="77fc4-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="77fc4-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77fc4-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="77fc4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="77fc4-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="77fc4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77fc4-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="77fc4-105">Attributes</span></span>  
  
|<span data-ttu-id="77fc4-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="77fc4-106">Attribute</span></span>|<span data-ttu-id="77fc4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="77fc4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77fc4-108">typ</span><span class="sxs-lookup"><span data-stu-id="77fc4-108">type</span></span>|<span data-ttu-id="77fc4-109">Nazwa typu CLR programu obsługi tokenów, który ma zostać dodany.</span><span class="sxs-lookup"><span data-stu-id="77fc4-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="77fc4-110">Aby uzyskać więcej informacji na temat sposobu określania `type` atrybutu, zobacz [odwołania do typów niestandardowych](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="77fc4-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77fc4-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="77fc4-111">Child Elements</span></span>  
  
|<span data-ttu-id="77fc4-112">Element</span><span class="sxs-lookup"><span data-stu-id="77fc4-112">Element</span></span>|<span data-ttu-id="77fc4-113">Opis</span><span class="sxs-lookup"><span data-stu-id="77fc4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="77fc4-114">Zapewnia konfigurację <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> klasy, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> klasy lub klasy pochodnej jednej z tych klas.</span><span class="sxs-lookup"><span data-stu-id="77fc4-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="77fc4-115">Zapewnia konfigurację <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> klasy lub klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="77fc4-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="77fc4-116">Zapewnia konfigurację <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> klasy lub klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="77fc4-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="77fc4-117">Zapewnia opcjonalną konfigurację <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> klasy lub klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="77fc4-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77fc4-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="77fc4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="77fc4-119">Element</span><span class="sxs-lookup"><span data-stu-id="77fc4-119">Element</span></span>|<span data-ttu-id="77fc4-120">Opis</span><span class="sxs-lookup"><span data-stu-id="77fc4-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="77fc4-121">Określa kolekcję programów obsługi tokenów zabezpieczających, które są zarejestrowane w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="77fc4-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77fc4-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="77fc4-122">Remarks</span></span>  
 <span data-ttu-id="77fc4-123">`<add>`Element może przyjmować jeden element podrzędny, który określa konfigurację programu obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="77fc4-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="77fc4-124">Jest to zależne od tego, czy Klasa obsługi, do której odwołuje się `type` atrybut `<add>` elementu, zapewnia obsługę tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="77fc4-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="77fc4-125">Klasy obsługi tokenów, które udostępniają tę funkcję, muszą uwidaczniać Konstruktor, który pobiera <xref:System.Xml.XmlElement> obiekt.</span><span class="sxs-lookup"><span data-stu-id="77fc4-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="77fc4-126">Niektóre wbudowane klasy procedury obsługi tokenów zabezpieczających zapewniają tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="77fc4-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="77fc4-127">Te klasy to <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> i <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="77fc4-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77fc4-128">Kolekcja obsługi tokenów może zawierać tylko jedną procedurę obsługi dla danego typu.</span><span class="sxs-lookup"><span data-stu-id="77fc4-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="77fc4-129">Oznacza to, na przykład, że jeśli chcesz dodać program obsługi, który pochodzi od <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> klasy do kolekcji, musisz najpierw usunąć element <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , który jest domyślnie obecny, z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="77fc4-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="77fc4-130">Możesz użyć elementu, [\<remove>](remove.md) Aby usunąć pojedynczą procedurę obsługi z kolekcji lub użyć elementu, [\<clear>](clear.md) Aby usunąć wszystkie programy obsługi z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="77fc4-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="77fc4-131">Ustawienia określone w ustawieniach przesłonięcia programu obsługi określone w kolekcji obsługi tokenów w [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemencie i określonych na poziomie usługi w ramach [\<identityConfiguration>](identityconfiguration.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="77fc4-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77fc4-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="77fc4-132">Example</span></span>  
 <span data-ttu-id="77fc4-133">Poniższy kod XML pokazuje użycie `<add>` elementów i, `<remove>` Aby zastąpić domyślną procedurę obsługi tokena sesji za pomocą procedury obsługi niestandardowego tokenu sesji.</span><span class="sxs-lookup"><span data-stu-id="77fc4-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="77fc4-134">KOD XML jest pobierany z `ClaimsAwareWebFarm` przykładu.</span><span class="sxs-lookup"><span data-stu-id="77fc4-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
