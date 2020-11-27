---
title: Negocjacje i limity czasu dotyczące zabezpieczeń
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 4ccc7e5539b1a772be6f9edb5a4cb4d94a8d1c1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275986"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="6f813-102">Negocjacje i limity czasu dotyczące zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="6f813-102">Security Negotiation and Timeouts</span></span>

<span data-ttu-id="6f813-103">Po uwierzytelnieniu klientów i usług Windows Communication Foundation (WCF) obsługuje tryb, w którym poświadczenia usługi są negocjowane w ramach uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="6f813-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="6f813-104">W takich scenariuszach potencjalnie wymiana wieloetapowa odbywa się między klientem a usługą w celu propagowania poświadczeń usługi do klienta programu.</span><span class="sxs-lookup"><span data-stu-id="6f813-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="6f813-105"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>Właściwość określa, jak długo można wykonać wymianę Wieloetapową.</span><span class="sxs-lookup"><span data-stu-id="6f813-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="6f813-106">Jednak ten limit czasu ma zastosowanie tylko wtedy, gdy program Exchange rzeczywiście pobiera więcej z pojedynczej odpowiedzi na żądanie.</span><span class="sxs-lookup"><span data-stu-id="6f813-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="6f813-107">W przypadkach, gdy negocjowanie kończy się pojedynczym rejsem, limit czasu nie ma zastosowania.</span><span class="sxs-lookup"><span data-stu-id="6f813-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f813-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f813-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="6f813-109">Instrukcje: ustawianie maksymalnego przesunięcia czasowego zegara</span><span class="sxs-lookup"><span data-stu-id="6f813-109">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)
