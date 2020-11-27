---
title: Zagadnienia dotyczące zabezpieczeń bezpiecznych sesji
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: abfbb565e06059e05eda3900ba9b8769e3657af8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276038"
---
# <a name="security-considerations-for-secure-sessions"></a>Zagadnienia dotyczące zabezpieczeń bezpiecznych sesji

Podczas implementowania bezpiecznych sesji należy wziąć pod uwagę następujące elementy, które mają wpływ na zabezpieczenia. Aby uzyskać więcej informacji na temat zagadnień związanych z zabezpieczeniami, zobacz [zagadnienia dotyczące zabezpieczeń](security-considerations-in-wcf.md) i [najlepsze rozwiązania w zakresie zabezpieczeń](best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Zabezpieczanie sesji i metadanych  

 Gdy zostanie ustanowiona bezpieczna sesja i <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> Właściwość jest ustawiona na `false` , Windows Communication Foundation (WCF) wysyła `mssp:MustNotSendCancel` potwierdzenie jako część metadanych w dokumencie Web Services Description Language (WSDL) dla punktu końcowego usługi. `mssp:MustNotSendCancel`Potwierdzenie informuje klientów, że usługa nie odpowiada na żądania anulowania bezpiecznej sesji. Gdy <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> Właściwość jest ustawiona na `true` , funkcja WCF nie emituje `mssp:MustNotSendCancel` potwierdzenia w dokumencie WSDL. Klienci oczekują wysłania żądania anulowania do usługi, gdy nie wymagają już bezpiecznej sesji. Gdy klient zostanie wygenerowany przy użyciu [Narzędzia do przesyłania metadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md), kod klienta reaguje odpowiednio na obecność lub brak `mssp:MustNotSendCancel` potwierdzenia.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Bezpieczne konwersacje i tokeny niestandardowe  

 Występują problemy z mieszaniem niestandardowych tokenów i kluczy pochodnych ze względu na sposób ich zdefiniowania w specyfikacji WS-SecureConversation. Specyfikacja wskazuje, że `wsse:SecurityTokenReference` jest opcjonalny element, który odwołuje się do tokenu pochodnego: " `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` ten element opcjonalny jest używany do określania tokenu kontekstu zabezpieczeń, tokenu zabezpieczającego lub klucza współużytkowanego/tajnego używanego do wyprowadzania. Jeśli nie zostanie określony, zakłada się, że odbiorca może określić klucz współużytkowany z kontekstu komunikatów. Jeśli nie można określić kontekstu, `wsc:UnknownDerivationSource` powinien zostać wywołany błąd, taki jak.  
  
 Oznacza to, że jeśli chcesz, aby Token niestandardowy był pochodny, należy otoczyć jego typ klauzuli w `SecurityTokenReference` elemencie. Istnieje możliwość wyłączenia wyprowadzania, ale domyślnie klucze pochodne. Jeśli nie udało się otoczyć klucza, Serializowanie tokenu klucza pochodnego powiedzie się, ale próba jego deserializacji zgłosi wyjątek.  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: wyłączanie bezpiecznej sesji przy użyciu klasy WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Zagadnienia dotyczące zabezpieczeń](security-considerations-in-wcf.md)
- [Najlepsze rozwiązania dotyczące zabezpieczeń](best-practices-for-security-in-wcf.md)
