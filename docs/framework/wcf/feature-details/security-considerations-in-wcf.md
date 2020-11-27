---
title: Zagadnienia dotyczące zabezpieczeń w programie WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 796098258601ec5fa208fd8a8060b28c3eeeb4d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276025"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="7517f-102">Zagadnienia dotyczące zabezpieczeń w programie WCF</span><span class="sxs-lookup"><span data-stu-id="7517f-102">Security Considerations in WCF</span></span>

<span data-ttu-id="7517f-103">W tematach w tej sekcji przedstawiono różne elementy związane z zabezpieczeniami, które należy wziąć pod uwagę podczas projektowania aplikacji Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7517f-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7517f-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="7517f-104">In This Section</span></span>  

 [<span data-ttu-id="7517f-105">Information Disclosure (ujawnienie informacji)</span><span class="sxs-lookup"><span data-stu-id="7517f-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="7517f-106">W tym artykule omówiono różne sposoby, w których informacje mogą być ujawnione lub zaatakowane oraz jak można je złagodzić.</span><span class="sxs-lookup"><span data-stu-id="7517f-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="7517f-107">Elevation of Privilege (podniesienie uprawnień)</span><span class="sxs-lookup"><span data-stu-id="7517f-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="7517f-108">W tym artykule omówiono skutki udzielenia uprawnień autoryzacji osoby atakującej poza tymi, które zostały początkowo przyznane i jak można je złagodzić.</span><span class="sxs-lookup"><span data-stu-id="7517f-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="7517f-109">Denial of Service (odmowa usługi)</span><span class="sxs-lookup"><span data-stu-id="7517f-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="7517f-110">W tym artykule omówiono, co się dzieje, gdy system nie może prawidłowo przetwarzać komunikatów i jak można je ograniczyć.</span><span class="sxs-lookup"><span data-stu-id="7517f-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="7517f-111">Tampering (manipulowanie)</span><span class="sxs-lookup"><span data-stu-id="7517f-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="7517f-112">W tym artykule omówiono zmiany komunikatów lub dostarczania komunikatów oraz sposób ich ograniczania.</span><span class="sxs-lookup"><span data-stu-id="7517f-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="7517f-113">Ataki oparte na metodzie powtórzeń</span><span class="sxs-lookup"><span data-stu-id="7517f-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="7517f-114">W tym artykule omówiono, co się dzieje, gdy osoba atakująca skopiuje strumień komunikatów między dwiema stronami i odtwarza strumień do jednej lub kilku stron, a także jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="7517f-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="7517f-115">Zagadnienia dotyczące zabezpieczeń bezpiecznych sesji</span><span class="sxs-lookup"><span data-stu-id="7517f-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="7517f-116">W tym artykule omówiono następujące elementy, które mają wpływ na zabezpieczenia podczas implementowania bezpiecznych sesji.</span><span class="sxs-lookup"><span data-stu-id="7517f-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="7517f-117">Nieobsługiwane scenariusze</span><span class="sxs-lookup"><span data-stu-id="7517f-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="7517f-118">Wyświetla listę różnych scenariuszy, które nie obsługują określonego aspektu zabezpieczeń i należy je unikać lub rozważać.</span><span class="sxs-lookup"><span data-stu-id="7517f-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7517f-119">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="7517f-119">Reference</span></span>  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="7517f-120">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="7517f-120">Related Sections</span></span>  

 [<span data-ttu-id="7517f-121">Wytyczne dotyczące zabezpieczeń i najlepsze rozwiązania</span><span class="sxs-lookup"><span data-stu-id="7517f-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="7517f-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7517f-122">See also</span></span>

- [<span data-ttu-id="7517f-123">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="7517f-123">Security</span></span>](security.md)
