---
title: Używanie wielu schematów uwierzytelniania z programem WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 3aae9bff4300af97f7b179d9d8115340a26e715a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289428"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="bcf2f-102">Używanie wielu schematów uwierzytelniania z programem WCF</span><span class="sxs-lookup"><span data-stu-id="bcf2f-102">Using Multiple Authentication Schemes with WCF</span></span>

<span data-ttu-id="bcf2f-103">Funkcja WCF umożliwia teraz określenie wielu schematów uwierzytelniania w jednym punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="bcf2f-104">Ponadto usługi hostowane w sieci Web mogą dziedziczyć ustawienia uwierzytelniania bezpośrednio z usług IIS.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="bcf2f-105">Usługi samoobsługowe mogą określać, które schematy uwierzytelniania mogą być używane.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="bcf2f-106">Aby uzyskać więcej informacji na temat ustawiania ustawień uwierzytelniania w usługach IIS, zobacz [uwierzytelnianie usług IIS](https://go.microsoft.com/fwlink/?LinkId=232458) .</span><span class="sxs-lookup"><span data-stu-id="bcf2f-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="bcf2f-107">Usługi IIS-Hosted</span><span class="sxs-lookup"><span data-stu-id="bcf2f-107">IIS-Hosted Services</span></span>  

 <span data-ttu-id="bcf2f-108">W przypadku usług hostowanych przez usługi IIS Ustaw schematy uwierzytelniania, które mają być używane w usługach IIS.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="bcf2f-109">Następnie w pliku web.config usługi w konfiguracji powiązania Określ obiekt clientCredential Type jako "InheritedFromHost", jak pokazano w poniższym fragmencie kodu XML:</span><span class="sxs-lookup"><span data-stu-id="bcf2f-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="bcf2f-110">Można określić, że tylko podzbiór schematów uwierzytelniania ma być używany z usługą przy użyciu ServiceAuthenticationBehavior lub \<serviceAuthenticationManager> elementu.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="bcf2f-111">Podczas konfigurowania tego programu w kodzie Użyj ServiceAuthenticationBehavior, jak pokazano w poniższym fragmencie kodu.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="bcf2f-112">W przypadku konfigurowania tego elementu w pliku konfiguracji, należy użyć \<serviceAuthenticationManager> element, jak pokazano w poniższym fragmencie kodu XML.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="bcf2f-113">Zapewni to, że tylko podzestaw schematów uwierzytelniania wymienionych w tym miejscu zostanie uwzględniony w punkcie końcowym usługi, w zależności od tego, co jest wybrane w usługach IIS.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="bcf2f-114">Oznacza to, że deweloper może wykluczyć uwierzytelnianie podstawowe na liście, pomijając je z listy ServiceAuthenticationManager, a nawet jeśli jest włączona w usługach IIS, nie zostanie zastosowana w punkcie końcowym usługi.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="bcf2f-115">Usługi Self-Hosted</span><span class="sxs-lookup"><span data-stu-id="bcf2f-115">Self-Hosted Services</span></span>  

 <span data-ttu-id="bcf2f-116">Usługi samoobsługowe są skonfigurowane nieco inaczej, ponieważ nie ma żadnych usług IIS do dziedziczenia ustawień.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="bcf2f-117">W tym miejscu Użyj \<serviceAuthenticationManager> elementu lub ServiceAuthenticationBehavior, aby określić ustawienia uwierzytelniania, które będą dziedziczone.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="bcf2f-118">W kodzie wygląda to następująco:</span><span class="sxs-lookup"><span data-stu-id="bcf2f-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="bcf2f-119">W konfiguracji wygląda to następująco:</span><span class="sxs-lookup"><span data-stu-id="bcf2f-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="bcf2f-120">A następnie można określić InheritFromHost w ustawieniach powiązania, jak pokazano w poniższym fragmencie kodu XML.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="bcf2f-121">Alternatywnie możesz określić schematy uwierzytelniania w niestandardowym powiązaniu, ustawiając schematy uwierzytelniania w elemencie powiązania transportu HTTP, jak pokazano w poniższym fragmencie kodu.</span><span class="sxs-lookup"><span data-stu-id="bcf2f-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcf2f-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bcf2f-122">See also</span></span>

- [<span data-ttu-id="bcf2f-123">Wiązania i zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="bcf2f-123">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="bcf2f-124">Punkty końcowe: adresy, wiązania i kontrakty</span><span class="sxs-lookup"><span data-stu-id="bcf2f-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="bcf2f-125">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="bcf2f-125">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="bcf2f-126">Możliwości zabezpieczeń wiązań niestandardowych</span><span class="sxs-lookup"><span data-stu-id="bcf2f-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="bcf2f-127">Powiązania</span><span class="sxs-lookup"><span data-stu-id="bcf2f-127">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="bcf2f-128">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="bcf2f-128">Custom Bindings</span></span>](../extending/custom-bindings.md)
