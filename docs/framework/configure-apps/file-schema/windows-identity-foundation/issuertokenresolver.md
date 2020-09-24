---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 946ae8601e1e4563becd0b346b6c792724405a45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165042"
---
# \<issuerTokenResolver>

<span data-ttu-id="8cf5a-101">Rejestruje program rozpoznawania tokenów wystawcy, który jest używany przez programy obsługi w kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8cf5a-102">Program rozpoznawania tokenów wystawcy służy do rozpoznawania tokenu podpisywania w przypadku przychodzących tokenów i komunikatów.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="8cf5a-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="8cf5a-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cf5a-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8cf5a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8cf5a-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cf5a-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8cf5a-106">Attributes</span></span>  
  
|<span data-ttu-id="8cf5a-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8cf5a-107">Attribute</span></span>|<span data-ttu-id="8cf5a-108">Opis</span><span class="sxs-lookup"><span data-stu-id="8cf5a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8cf5a-109">typ</span><span class="sxs-lookup"><span data-stu-id="8cf5a-109">type</span></span>|<span data-ttu-id="8cf5a-110">Określa typ programu rozpoznawania tokenów wystawcy.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="8cf5a-111">Musi być <xref:System.IdentityModel.Tokens.IssuerTokenResolver> klasą lub typem, który pochodzi od <xref:System.IdentityModel.Tokens.IssuerTokenResolver> klasy.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="8cf5a-112">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cf5a-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8cf5a-113">Child Elements</span></span>  

 <span data-ttu-id="8cf5a-114">Brak</span><span class="sxs-lookup"><span data-stu-id="8cf5a-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8cf5a-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8cf5a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8cf5a-116">Element</span><span class="sxs-lookup"><span data-stu-id="8cf5a-116">Element</span></span>|<span data-ttu-id="8cf5a-117">Opis</span><span class="sxs-lookup"><span data-stu-id="8cf5a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="8cf5a-118">Zapewnia konfigurację kolekcji programów obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cf5a-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8cf5a-119">Remarks</span></span>  

 <span data-ttu-id="8cf5a-120">Program rozpoznawania tokenów wystawcy służy do rozpoznawania tokenu podpisywania w przypadku przychodzących tokenów i komunikatów.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="8cf5a-121">Służy do pobierania materiału kryptograficznego, który jest używany do sprawdzania podpisu.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="8cf5a-122">Należy określić `type` atrybut.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="8cf5a-123">Określony typ może być albo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> typem niestandardowym, który pochodzi od <xref:System.IdentityModel.Tokens.IssuerTokenResolver> klasy.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="8cf5a-124">Niektóre programy obsługi tokenów umożliwiają określenie ustawień programu rozpoznawania tokenów wystawcy w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="8cf5a-125">Ustawienia poszczególnych programów obsługi tokenów przesłaniają te określone w kolekcji obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cf5a-126">Określanie `<issuerTokenResolver>` elementu jako elementu podrzędnego [\<identityConfiguration>](identityconfiguration.md) elementu jest przestarzałe, ale nadal jest ono obsługiwane w celu zapewnienia zgodności z poprzednimi wersjami.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="8cf5a-127">Ustawienia w `<securityTokenHandlerConfiguration>` elemencie Przesłoń te elementy w `<identityConfiguration>` elemencie.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cf5a-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="8cf5a-128">Example</span></span>  

 <span data-ttu-id="8cf5a-129">W poniższym kodzie XML przedstawiono konfigurację programu rozpoznawania tokenów wystawcy opartą na niestandardowej klasie, która pochodzi od <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="8cf5a-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="8cf5a-130">Program rozpoznawania tokenów obsługuje słownik par kluczy odbiorców, które są inicjowane z niestandardowego elementu konfiguracji ( `<AddAudienceKeyPair>` ) zdefiniowanego dla klasy.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="8cf5a-131">Klasa przesłania <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodę w celu przetworzenia tego elementu.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="8cf5a-132">Przesłonięcie pokazano w następującym przykładzie: jednak metody, które wywołuje, nie są wyświetlane dla zwięzłości.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="8cf5a-133">Aby uzyskać pełny przykład, zobacz `CustomToken` przykład.</span><span class="sxs-lookup"><span data-stu-id="8cf5a-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="8cf5a-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="8cf5a-134">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="8cf5a-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8cf5a-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
