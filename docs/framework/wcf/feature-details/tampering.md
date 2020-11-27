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
# <a name="tampering"></a>Tampering (manipulowanie)

*Manipulowanie* to czynność polegająca na zmianie wiadomości lub dostarczeniu wiadomości, a także przy użyciu zmienionego komunikatu do celów innych niż to, do czego została zaprojektowana.  
  
## <a name="do-not-disable-ws-addressing"></a>Nie wyłączaj WS-Addressing  

 Specyfikacja WS-Addressing zawiera nagłówki adresów dla każdego komunikatu, umożliwiając odbiorcom komunikatu zweryfikowanie nadawcy wiadomości. Tę funkcję można wyłączyć, ustawiając <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> Właściwość na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .  
  
 Gdy tryb zabezpieczeń jest ustawiony na komunikat, a jeśli WS-Addressing jest wyłączona, osoba atakująca może wykonać żądanie od klienta i wysłać ją do innej usługi, a druga usługa nie ma możliwości wykrycia, że wiadomość pochodzi od oryginalnego klienta. W efekcie pierwsza usługa może poudawać, że jest klientem podczas rozmowy z drugą usługą.  
  
 Aby rozwiązać ten problem, nigdy nie ustawiaj <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> właściwości na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> i Unikaj używania <xref:System.ServiceModel.Channels.MessageVersion> , takich jak właściwość statyczna <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> , która ustawia <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> Właściwość na <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .  
  
## <a name="see-also"></a>Zobacz też

- [Zagadnienia dotyczące zabezpieczeń](security-considerations-in-wcf.md)
- [Information Disclosure (ujawnienie informacji)](information-disclosure.md)
- [Elevation of Privilege (podniesienie uprawnień)](elevation-of-privilege.md)
- [Denial of Service (odmowa usługi)](denial-of-service.md)
- [Nieobsługiwane scenariusze](unsupported-scenarios.md)
- [Ataki oparte na metodzie powtórzeń](replay-attacks.md)
