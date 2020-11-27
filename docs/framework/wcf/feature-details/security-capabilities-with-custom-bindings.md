---
title: Możliwości zabezpieczeń wiązań niestandardowych
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288310"
---
# <a name="security-capabilities-with-custom-bindings"></a>Możliwości zabezpieczeń wiązań niestandardowych

Większość typowych zadań związanych z zabezpieczeniami można wykonać przy użyciu jednego z powiązań dostarczonych przez system. Jeśli potrzebujesz więcej kontroli, możesz jednak utworzyć niestandardowe powiązanie z <xref:System.ServiceModel.Channels.SecurityBindingElement> , zgodnie z opisem w poniższych tematach. Aby uzyskać więcej informacji na temat powiązań niestandardowych, zobacz [niestandardowe powiązania](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Tryby uwierzytelniania elementu SecurityBindingElement](securitybindingelement-authentication-modes.md)  
 Zawiera opis trybów uwierzytelniania, które są możliwe przy użyciu niestandardowego powiązania.  
  
 [Instrukcje: tworzenie niestandardowego wiązania za pomocą elementu SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Opisuje podstawowe kroki tworzenia powiązania niestandardowego z elementem zabezpieczeń.  
  
 [Instrukcje: tworzenie elementu SecurityBindingElement dla określonego trybu uwierzytelniania](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Opisuje sposób tworzenia elementu zabezpieczeń dla określonego trybu uwierzytelniania.  
  
 [Instrukcje: wyłączanie bezpiecznej sesji przy użyciu klasy WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Opisuje sposób wyłączania bezpiecznych sesji podczas tworzenia usługi federacyjnej.  
  
 [Instrukcje: włączanie wykrywania powtarzania komunikatu](how-to-enable-message-replay-detection.md)  
 Opisuje sposób określania, kiedy występuje atak powtarzający się.  
  
 [Instrukcje: tworzenie poświadczeń pomocniczych](how-to-create-a-supporting-credential.md)  
 Zawiera opis sposobu dostarczania poświadczenie pomocnicze do usługi, jeśli jest to wymagane przez usługę.  
  
 [Instrukcje: konfigurowanie potwierdzenia sygnatury](how-to-set-up-a-signature-confirmation.md)  
 W tym artykule opisano kroki umożliwiające potwierdzenie podpisów podczas cyfrowego podpisywania komunikatów.  
  
 [Instrukcje: ustawianie maksymalnego przesunięcia czasowego zegara](how-to-set-a-max-clock-skew.md)  
 Opisuje sposób ustawienia maksymalnej dozwolonej różnicy czasu między usługą a klientem.  
  
 [Instrukcje: wyłączanie szyfrowania podpisów cyfrowych](how-to-disable-encryption-of-digital-signatures.md)  
 Opisuje, jak wyłączenie szyfrowania podpisów cyfrowych może przynieść korzyści z wydajności.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Omówienie poziomów ochrony](../understanding-protection-level.md)  
  
 [Zabezpieczanie usług i klientów](securing-services-and-clients.md)  
  
## <a name="see-also"></a>Zobacz też

- [Wiązania i zabezpieczenia](bindings-and-security.md)
- [Przegląd zabezpieczeń](security-overview.md)
- [Wiązania dostarczane przez system](../system-provided-bindings.md)
