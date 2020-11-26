---
title: WSDL i zasady
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: 123a878e90ee9099b009985a5e79155e8b1cd097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238343"
---
# <a name="wsdl-and-policy"></a>WSDL i zasady

W tym temacie omówiono Windows Communication Foundation (WCF) WSDL 1,1, WS-Policy i WS-PolicyAttachment szczegóły implementacji, a także dodatkowe WS-Policy potwierdzenia i rozszerzenia WSDL 1,1 wprowadzone przez WCF.  
  
 Usługa WCF implementuje specyfikacje WS-Policy i WS-PolicyAttachment przesłane do pliku W3C z ograniczeniami i wyjaśnieniami opisanymi w tym dokumencie.  
  
 W tym dokumencie są stosowane prefiksy i przestrzenie nazw podane w poniższej tabeli.  
  
|Prefiks|Przestrzeń nazw|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|wsp (WS-Policy 1,5)|`http://www.w3.org/ns/ws-policy`|  
|http|`http://schemas.microsoft.com/ws/06/2004/policy/http`|  
|usługą|`http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq`|  
|MSF|`http://schemas.microsoft.com/ws/2006/05/framing/policy`|  
|mssp|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
|MSC|`http://schemas.microsoft.com/ws/2005/12/wsdl/contract`|  
|CDP|`http://schemas.microsoft.com/net/2006/06/duplex`|  
  
## <a name="wcf-wsdl11-extensions"></a>Rozszerzenia języka WSDL WCF 1.1  

 Program WCF używa następujących rozszerzeń WSDL 1.1 do opisywania wymagań dotyczących sesji kontraktu.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 XS: Boolean, wskazuje, że ta operacja inicjuje sesję WCF; wartość domyślna to `false` .  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 XS: wartość logiczna wskazuje, że ta operacja kończy sesję WCF; wartość domyślna to `false` .  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 XS: wartość logiczna wskazuje, że ten kontrakt wymaga ustanowienia sesji.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>Identyfikatory URI transportu protokołu SOAP 1. x  

 Funkcja WCF używa następujących identyfikatorów URI, aby wskazać transporty, które mają być używane dla elementów WSDL 1,1, SOAP 1,1 i SOAP 1,2 powiązania.  
  
|Transport|URI|  
|---------------|---------|  
|HTTP|`http://schemas.xmlsoap.org/soap/http`|  
|TCP|`http://schemas.microsoft.com/soap/tcp`|  
|Usługa MSMQ|`http://schemas.microsoft.com/soap/msmq`|  
|Nazwane potoki|`http://schemas.microsoft.com/soap/named-pipe`|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Potwierdzenia zasad implementowane przez WCF  

 Oprócz potwierdzeń zasad wprowadzonych w specyfikacjach usług sieci Web (WS-*) i wymienionych w innych sekcjach tego dokumentu, WCF implementuje następujące potwierdzenia zasad.  
  
|Potwierdzenie zasad|Podmiot zasad|Opis|  
|----------------------|--------------------|-----------------|  
|http: HttpBasicAuthentication|Punkt końcowy|Punkt końcowy używa uwierzytelniania podstawowego protokołu HTTP.|  
|http: HttpDigestAuthentication|Punkt końcowy|Punkt końcowy używa uwierzytelniania szyfrowanego protokołu HTTP.|  
|http: HttpNegotiateAuthentication|Punkt końcowy|Punkt końcowy używa uwierzytelniania przy użyciu protokołu HTTP.|  
|http: HttpNtlmAuthentication|Punkt końcowy|Punkt końcowy używa uwierzytelniania HTTP NTLM.|  
|MSF: przesyłane strumieniowo|Punkt końcowy|Punkt końcowy używa ramek komunikatów przesyłanych strumieniowo. To potwierdzenie jest używane z protokołem ramek komunikatów udostępnianym do transportów, takich jak TCP i nazwane potoki.|  
|MSF: SslTransportSecurity|Punkt końcowy|Punkt końcowy używa protokołu TLS (Transport Layer Security) z ramkami komunikatów.|  
|MSF: WindowsTransportSecurity|Punkt końcowy|Punkt końcowy używa negocjacji dostawcy zabezpieczeń (SPNEGO) z ramkami komunikatów.|  
|MSMQ: MsmqBestEffort|Punkt końcowy|Usługa MSMQ z gwarancjami najlepszego wysiłku.|  
|MSMQ: MsmqSession|Punkt końcowy|Usługa MSMQ z gwarancjami sesji.|  
|MSMQ: MsmqVolatile|Punkt końcowy|Nietrwała usługa MSMQ.|  
|MSMQ: uwierzytelnione|Punkt końcowy|Uwierzytelnianie jest używane z transportem usługi MSMQ.|  
|MSMQ: WindowsDomain|Punkt końcowy|Usługa MSMQ używa uwierzytelniania domeny systemu Windows.|  
|CDP: CompositeDuplex|Punkt końcowy|Punkt końcowy używa dwóch oddzielnych połączeń Transverse transportowej dla komunikatów in i out.|  
|mssp:RsaToken|Zagnieżdżone|Potwierdzenie tokenu klucza RSA. To wymaganie jest zwykle spełnione przez Serializowanie klucza RSA bezpośrednio jako część najważniejszych informacji w podpisie poświadczanym.|  
|mssp:SslContextToken|Zagnieżdżone|Wymaga, aby SecurityContextToken uzyskany przy użyciu binarnego uzgadniania TLS przy użyciu WS-Trust. Zagnieżdżone potwierdzenia obejmują: SP: RequireDerivedKeys, mssp: MustNotSendCancel, mssp: RequireClientCertificate.|  
|mssp:MustNotSendCancel|Zagnieżdżone|Określa wymaganie, aby komunikaty żądania tokenu zabezpieczającego żądania (RST) [WS-Trust] za pomocą anulowania powiązania [WS-Trust, WS-SC] nie były wysyłane do wystawcy danego SecurityContextToken. Jeśli to potwierdzenie jest obecne, takie komunikaty żądania nie mogą być wysyłane do wystawcy. Jeśli to potwierdzenie nie istnieje, takie komunikaty żądania mogą być wysyłane do wystawcy.|  
|mssp:RequireClientCertificate|Zagnieżdżone|Ten opcjonalny element określa wymaganie, aby certyfikat klienta był dostarczany jako część protokołu TLSNEGO. Jeśli to potwierdzenie jest obecne, należy podać certyfikat klienta. Jeśli to potwierdzenie nie istnieje, nie można podać certyfikatu klienta. Nie można używać tego potwierdzenia poza mssp: SslContextToken.|  
  
## <a name="see-also"></a>Zobacz też

- [Niestandardowa publikacja WSDL](../samples/custom-wsdl-publication.md)
- [Instrukcje: eksportowanie niestandardowych informacji w formacie WSDL](../extending/how-to-export-custom-wsdl.md)
- [Instrukcje: importowanie niestandardowych plików WSDL](../extending/how-to-import-custom-wsdl.md)
