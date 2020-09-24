---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 9991430f09cb6a63d0a3cdde24a4ff03d3dd746d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165055"
---
# \<issuerNameRegistry>

<span data-ttu-id="f43fb-101">Konfiguruje rejestr nazw wystawców, który jest używany przez programy obsługi w kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="f43fb-101">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="f43fb-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="f43fb-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f43fb-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f43fb-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f43fb-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f43fb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f43fb-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f43fb-105">Attributes</span></span>  
  
|<span data-ttu-id="f43fb-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f43fb-106">Attribute</span></span>|<span data-ttu-id="f43fb-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f43fb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f43fb-108">typ</span><span class="sxs-lookup"><span data-stu-id="f43fb-108">type</span></span>|<span data-ttu-id="f43fb-109">Typ, który pochodzi od <xref:System.IdentityModel.Tokens.IssuerNameRegistry> klasy.</span><span class="sxs-lookup"><span data-stu-id="f43fb-109">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="f43fb-110">Aby uzyskać więcej informacji na temat sposobu określania niestandardowego `type` , zobacz [odwołania do typów niestandardowych].</span><span class="sxs-lookup"><span data-stu-id="f43fb-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f43fb-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f43fb-111">Child Elements</span></span>  
  
|<span data-ttu-id="f43fb-112">Element</span><span class="sxs-lookup"><span data-stu-id="f43fb-112">Element</span></span>|<span data-ttu-id="f43fb-113">Opis</span><span class="sxs-lookup"><span data-stu-id="f43fb-113">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="f43fb-114">Gdy `type` atrybut określa rejestr nazw wystawcy oparty na konfiguracji ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasa), [\<trustedIssuers>](trustedissuers.md) należy określić element.</span><span class="sxs-lookup"><span data-stu-id="f43fb-114">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="f43fb-115">[\<trustedIssuers>](trustedissuers.md)Element może przyjmować `<add>` , `<clear>` , lub `<remove>` elementy jako elementy podrzędne.</span><span class="sxs-lookup"><span data-stu-id="f43fb-115">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f43fb-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f43fb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f43fb-117">Element</span><span class="sxs-lookup"><span data-stu-id="f43fb-117">Element</span></span>|<span data-ttu-id="f43fb-118">Opis</span><span class="sxs-lookup"><span data-stu-id="f43fb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="f43fb-119">Zapewnia konfigurację kolekcji programów obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="f43fb-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f43fb-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f43fb-120">Remarks</span></span>  

 <span data-ttu-id="f43fb-121">Wszystkie tokeny wystawcy są weryfikowane przy użyciu rejestru nazwy wystawcy.</span><span class="sxs-lookup"><span data-stu-id="f43fb-121">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="f43fb-122">Jest to obiekt, który pochodzi od <xref:System.IdentityModel.Tokens.IssuerNameRegistry> klasy.</span><span class="sxs-lookup"><span data-stu-id="f43fb-122">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="f43fb-123">Rejestr nazwy wystawcy służy do kojarzenia nazwy z materiałem kryptograficznym, który jest niezbędny do zweryfikowania podpisów tokenów wytworzonych przez odpowiedniego wystawcy.</span><span class="sxs-lookup"><span data-stu-id="f43fb-123">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="f43fb-124">Nazwa wystawcy Rejestr zawiera listę wystawców, które są zaufane przez aplikację jednostki uzależnionej (RP).</span><span class="sxs-lookup"><span data-stu-id="f43fb-124">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="f43fb-125">Typ rejestru Nazwa wystawcy jest określany przy użyciu `type` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="f43fb-125">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="f43fb-126">`<issuerNameRegistry>`Element może mieć co najmniej jeden element podrzędny, który zapewnia konfigurację określonego typu.</span><span class="sxs-lookup"><span data-stu-id="f43fb-126">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="f43fb-127">Należy podać logikę, która przetwarza te elementy podrzędne, zastępując <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="f43fb-127">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="f43fb-128">WIF zawiera typ rejestru o pojedynczej nazwie wystawcy z pola, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasa.</span><span class="sxs-lookup"><span data-stu-id="f43fb-128">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="f43fb-129">Ta klasa używa zestawu certyfikatów zaufanych wystawców, które są określone w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f43fb-129">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="f43fb-130">Wymaga podrzędnego elementu konfiguracji, `<trustedIssuers>` w którym jest skonfigurowana kolekcja certyfikatów zaufanych wystawców.</span><span class="sxs-lookup"><span data-stu-id="f43fb-130">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="f43fb-131">Certyfikaty zaufane są określane przy użyciu formy z certyfikatem ASN. 1 zaszyfrowanego odcisku palca certyfikatu i są dodawane lub usuwane z kolekcji przy użyciu `<add>` `<clear>` elementów, lub `<remove>` .</span><span class="sxs-lookup"><span data-stu-id="f43fb-131">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="f43fb-132">`<issuerNameRegistry>`Element jest reprezentowany przez <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> klasę.</span><span class="sxs-lookup"><span data-stu-id="f43fb-132">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f43fb-133">Określanie `<issuerNameRegistry>` elementu jako elementu podrzędnego [\<identityConfiguration>](identityconfiguration.md) elementu jest przestarzałe, ale nadal jest ono obsługiwane w celu zapewnienia zgodności z poprzednimi wersjami.</span><span class="sxs-lookup"><span data-stu-id="f43fb-133">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f43fb-134">Ustawienia w `<securityTokenHandlerConfiguration>` elemencie Przesłoń te elementy w `<identityConfiguration>` elemencie.</span><span class="sxs-lookup"><span data-stu-id="f43fb-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f43fb-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="f43fb-135">Example</span></span>  

 <span data-ttu-id="f43fb-136">W poniższym kodzie XML pokazano, jak określić nazwę rejestru wystawcy na podstawie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f43fb-136">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f43fb-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f43fb-137">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
