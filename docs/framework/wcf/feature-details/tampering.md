---
title: Tampering (manipulowanie)
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249803"
---
# <a name="tampering"></a><span data-ttu-id="13ab2-102">Tampering (manipulowanie)</span><span class="sxs-lookup"><span data-stu-id="13ab2-102">Tampering</span></span>

<span data-ttu-id="13ab2-103">*Manipulowanie* to czynność polegająca na zmianie wiadomości lub dostarczeniu wiadomości, a także przy użyciu zmienionego komunikatu do celów innych niż to, do czego została zaprojektowana.</span><span class="sxs-lookup"><span data-stu-id="13ab2-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="13ab2-104">Nie wyłączaj WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="13ab2-104">Do Not Disable WS-Addressing</span></span>  

 <span data-ttu-id="13ab2-105">Specyfikacja WS-Addressing zawiera nagłówki adresów dla każdego komunikatu, umożliwiając odbiorcom komunikatu zweryfikowanie nadawcy wiadomości.</span><span class="sxs-lookup"><span data-stu-id="13ab2-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="13ab2-106">Tę funkcję można wyłączyć, ustawiając <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> Właściwość na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="13ab2-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="13ab2-107">Gdy tryb zabezpieczeń jest ustawiony na komunikat, a jeśli WS-Addressing jest wyłączona, osoba atakująca może wykonać żądanie od klienta i wysłać ją do innej usługi, a druga usługa nie ma możliwości wykrycia, że wiadomość pochodzi od oryginalnego klienta.</span><span class="sxs-lookup"><span data-stu-id="13ab2-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="13ab2-108">W efekcie pierwsza usługa może poudawać, że jest klientem podczas rozmowy z drugą usługą.</span><span class="sxs-lookup"><span data-stu-id="13ab2-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="13ab2-109">Aby rozwiązać ten problem, nigdy nie ustawiaj <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> właściwości na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> i Unikaj używania <xref:System.ServiceModel.Channels.MessageVersion> , takich jak właściwość statyczna <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> , która ustawia <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> Właściwość na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="13ab2-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ab2-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13ab2-110">See also</span></span>

- [<span data-ttu-id="13ab2-111">Zagadnienia dotyczące zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="13ab2-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="13ab2-112">Information Disclosure (ujawnienie informacji)</span><span class="sxs-lookup"><span data-stu-id="13ab2-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="13ab2-113">Elevation of Privilege (podniesienie uprawnień)</span><span class="sxs-lookup"><span data-stu-id="13ab2-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="13ab2-114">Denial of Service (odmowa usługi)</span><span class="sxs-lookup"><span data-stu-id="13ab2-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="13ab2-115">Nieobsługiwane scenariusze</span><span class="sxs-lookup"><span data-stu-id="13ab2-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="13ab2-116">Ataki oparte na metodzie powtórzeń</span><span class="sxs-lookup"><span data-stu-id="13ab2-116">Replay Attacks</span></span>](replay-attacks.md)
