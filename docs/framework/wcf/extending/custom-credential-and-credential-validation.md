---
title: Niestandardowe poświadczenia i weryfikacja poświadczeń
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 5f2909bb088a5f3d3203fe3c9e24b2df3450aa3f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257831"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="9109f-102">Niestandardowe poświadczenia i weryfikacja poświadczeń</span><span class="sxs-lookup"><span data-stu-id="9109f-102">Custom Credential and Credential Validation</span></span>

<span data-ttu-id="9109f-103">Zabezpieczenia w programie Windows Communication Foundation (WCF) bazują na wymianie poświadczeń między usługami i klientami.</span><span class="sxs-lookup"><span data-stu-id="9109f-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="9109f-104">Większość scenariuszy zabezpieczeń można spełnić przy użyciu wspólnych typów poświadczeń, takich jak Windows (Kerberos), nazwa użytkownika i hasła oraz certyfikaty.</span><span class="sxs-lookup"><span data-stu-id="9109f-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="9109f-105">Jeśli jednak jest wymagany nowy typ poświadczeń, w tematach w tej sekcji wyjaśniono, jak obsługiwać i sprawdzać poprawność nowych typów.</span><span class="sxs-lookup"><span data-stu-id="9109f-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9109f-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="9109f-106">In This Section</span></span>  

 [<span data-ttu-id="9109f-107">Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów</span><span class="sxs-lookup"><span data-stu-id="9109f-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="9109f-108">Wyjaśnia, jak dostosować walidację programu WCF przez dziedziczenie z <xref:System.IdentityModel.Selectors.X509CertificateValidator> klasy.</span><span class="sxs-lookup"><span data-stu-id="9109f-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="9109f-109">Przewodnik: tworzenie niestandardowego klienta i poświadczeń usługi</span><span class="sxs-lookup"><span data-stu-id="9109f-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="9109f-110">Pokazuje, w jaki sposób można rozciągnąć <xref:System.ServiceModel.Description.ClientCredentials> klasy i, <xref:System.ServiceModel.Description.ServiceCredentials> aby pomieścić nowe typy poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="9109f-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="9109f-111">Jest to pierwsza część tematów, które umożliwiają tworzenie niestandardowych typów poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="9109f-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="9109f-112">Instrukcje: tworzenie niestandardowego dostawcy tokenów zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="9109f-112">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="9109f-113">Wyjaśnia, jak utworzyć dostawcę tokenów zabezpieczających do obsługi nowych typów poświadczeń i zwracać nowe tokeny dla poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="9109f-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="9109f-114">Jest to drugi temat w serii.</span><span class="sxs-lookup"><span data-stu-id="9109f-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="9109f-115">Instrukcje: tworzenie niestandardowego wystawcy uwierzytelniania tokenu zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="9109f-115">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="9109f-116">Wyjaśnia, jak utworzyć niestandardowy wystawca uwierzytelnienia w celu uwierzytelnienia nowego typu poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="9109f-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="9109f-117">Jest to trzeci temat w tej serii.</span><span class="sxs-lookup"><span data-stu-id="9109f-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9109f-118">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="9109f-118">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="9109f-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="9109f-119">Related Sections</span></span>  

 [<span data-ttu-id="9109f-120">Authentication</span><span class="sxs-lookup"><span data-stu-id="9109f-120">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="9109f-121">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="9109f-121">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="9109f-122">Autoryzacja</span><span class="sxs-lookup"><span data-stu-id="9109f-122">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9109f-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9109f-123">See also</span></span>

- [<span data-ttu-id="9109f-124">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="9109f-124">Security</span></span>](../feature-details/security.md)
