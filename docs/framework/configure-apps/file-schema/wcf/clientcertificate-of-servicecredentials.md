---
title: <clientCertificate> dla <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148920"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="361aa-102">\<clientCertificate> dla \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="361aa-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="361aa-103">Definiuje certyfikat X. 509 używany do podpisywania i szyfrowania komunikatów na kliencie, który tworzy usługę we wzorcu komunikacji dwukierunkowej.</span><span class="sxs-lookup"><span data-stu-id="361aa-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="361aa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="361aa-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="361aa-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="361aa-105">Attributes and Elements</span></span>  

 <span data-ttu-id="361aa-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="361aa-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="361aa-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="361aa-107">Attributes</span></span>  

 <span data-ttu-id="361aa-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="361aa-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="361aa-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="361aa-109">Child Elements</span></span>  
  
|<span data-ttu-id="361aa-110">Element</span><span class="sxs-lookup"><span data-stu-id="361aa-110">Element</span></span>|<span data-ttu-id="361aa-111">Opis</span><span class="sxs-lookup"><span data-stu-id="361aa-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="361aa-112">Określa opcje uwierzytelniania dla certyfikatu klienta.</span><span class="sxs-lookup"><span data-stu-id="361aa-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="361aa-113">Określa certyfikat, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="361aa-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="361aa-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="361aa-114">Parent Elements</span></span>  
  
|<span data-ttu-id="361aa-115">Element</span><span class="sxs-lookup"><span data-stu-id="361aa-115">Element</span></span>|<span data-ttu-id="361aa-116">Opis</span><span class="sxs-lookup"><span data-stu-id="361aa-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="361aa-117">Określa poświadczenia, które mają być używane w uwierzytelnianiu usługi oraz ustawienia powiązane z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="361aa-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="361aa-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="361aa-118">Remarks</span></span>  

 <span data-ttu-id="361aa-119">Ten element jest używany, gdy usługa musi uzyskać certyfikat klienta z wyprzedzeniem w celu bezpiecznego komunikowania się z klientem.</span><span class="sxs-lookup"><span data-stu-id="361aa-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="361aa-120">Dzieje się tak w przypadku używania wzorca komunikacji dupleksowej.</span><span class="sxs-lookup"><span data-stu-id="361aa-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="361aa-121">W przypadku bardziej typowego wzorca żądania/odpowiedzi klient zawiera swój certyfikat w żądaniu, którego usługa używa do szyfrowania i podpisywania odpowiedzi z powrotem do klienta.</span><span class="sxs-lookup"><span data-stu-id="361aa-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="361aa-122">W przypadku wzorca komunikacji dupleksowej usługa nie ma jednak żądania od klienta i w związku z tym potrzebuje certyfikatu klienta z wyprzedzeniem, aby zabezpieczyć komunikat do klienta.</span><span class="sxs-lookup"><span data-stu-id="361aa-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="361aa-123">W związku z tym należy uzyskać certyfikat klienta w negocjacji poza pasmem i określić certyfikat przy użyciu tego elementu.</span><span class="sxs-lookup"><span data-stu-id="361aa-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="361aa-124">Aby uzyskać więcej informacji na temat usług dupleksowych, zobacz [How to: Create a Duplex kontraktu](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="361aa-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="361aa-125">Certyfikat ustawiony w tym elemencie jest używany do szyfrowania komunikatów na kliencie tylko dla powiązań skonfigurowanych przy użyciu `MutualCertificateDuplex` trybu uwierzytelniania zabezpieczeń wiadomości.</span><span class="sxs-lookup"><span data-stu-id="361aa-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361aa-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="361aa-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="361aa-127">Instrukcje: tworzenie kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="361aa-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="361aa-128">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="361aa-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="361aa-129">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="361aa-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
