---
title: Uwierzytelnianie w programie WCF
description: Poznaj kilka mechanizmów w programie WCF, które zapewniają uwierzytelnianie, takie jak uwierzytelnianie systemu Windows, certyfikaty X. 509 i nazwa użytkownika i hasło.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: e2334a8c024238f38e1c927a278a4e25e7dabd9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247541"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="e3dea-103">Uwierzytelnianie w programie WCF</span><span class="sxs-lookup"><span data-stu-id="e3dea-103">Authentication in WCF</span></span>

<span data-ttu-id="e3dea-104">W poniższych tematach przedstawiono szereg różnych mechanizmów programu Windows Communication Foundation (WCF), które zapewniają uwierzytelnianie, na przykład uwierzytelnianie systemu Windows, certyfikaty X. 509 oraz nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="e3dea-104">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3dea-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="e3dea-105">In This Section</span></span>  

 [<span data-ttu-id="e3dea-106">Instrukcje: używanie dostawcy członkostwa platformy ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e3dea-106">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="e3dea-107">Funkcje ASP.NET obejmują członkostwo i dostawcę ról, bazę danych do przechowywania par nazw użytkowników i haseł na potrzeby uwierzytelniania oraz role użytkowników na potrzeby autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="e3dea-107">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="e3dea-108">W tym temacie wyjaśniono, w jaki sposób usługi WCF mogą używać tej samej bazy danych do uwierzytelniania i autoryzowania użytkowników.</span><span class="sxs-lookup"><span data-stu-id="e3dea-108">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="e3dea-109">Instrukcje: używanie niestandardowej nazwy użytkownika i modułu weryfikacji hasła</span><span class="sxs-lookup"><span data-stu-id="e3dea-109">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="e3dea-110">Pokazuje, jak zintegrować niestandardową nazwę użytkownika/moduł sprawdzania poprawności hasła.</span><span class="sxs-lookup"><span data-stu-id="e3dea-110">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="e3dea-111">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="e3dea-111">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="e3dea-112">Aby zapewnić dodatkową ochronę, klient może uwierzytelnić usługę, określając oczekiwaną *tożsamość* usługi.</span><span class="sxs-lookup"><span data-stu-id="e3dea-112">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="e3dea-113">Jeśli Oczekiwana tożsamość i tożsamość zwrócona przez usługę nie są zgodne, uwierzytelnianie kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e3dea-113">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="e3dea-114">Negocjacje i limity czasu dotyczące zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="e3dea-114">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="e3dea-115">Opisuje sposób użycia <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> właściwości w <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> klasie.</span><span class="sxs-lookup"><span data-stu-id="e3dea-115">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="e3dea-116">Debugowanie błędów uwierzytelniania systemu Windows</span><span class="sxs-lookup"><span data-stu-id="e3dea-116">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="e3dea-117">Koncentruje się na typowych problemach występujących podczas korzystania z uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="e3dea-117">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e3dea-118">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="e3dea-118">Reference</span></span>  

 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="e3dea-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="e3dea-119">Related Sections</span></span>  

 [<span data-ttu-id="e3dea-120">Typowe scenariusze zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="e3dea-120">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3dea-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3dea-121">See also</span></span>

- [<span data-ttu-id="e3dea-122">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="e3dea-122">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="e3dea-123">[Model zabezpieczeń dla sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e3dea-123">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
