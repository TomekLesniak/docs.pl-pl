---
title: 'Komunikacja podstawowa: kanały transportu HTTP-HTTPS'
ms.date: 03/30/2017
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
ms.openlocfilehash: 5d33d153c6c527398b035ad9d027593a0fefd0e8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277416"
---
# <a name="core-communications-httphttps-transport-channels"></a>Komunikacja podstawowa: Kanały transportu protokołów HTTP/HTTPS

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez kanały HTTP/HTTPS usługi Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Określono określony poziom personifikacji. Uwierzytelnianie szyfrowane HTTP obsługuje poziom "personifikacji" tylko wtedy, gdy jest używany z jawnym poświadczeniem.|  
|FramingContentTypeMismatch|Określony typ zawartości nie jest obsługiwany przez określoną usługę. Powiązania klienta i usługi mogą być niezgodne.|  
|Hosting_SslSettingsMisconfigured|Ustawienia SSL dla określonej usługi nie pasują do tych Internet Information Services.|  
|HttpAuthSchemeAndClientCert|Fabryka odbiorników HTTPS została skonfigurowana tak, aby wymagała certyfikatu klienta i określonego schematu uwierzytelniania. Jednak w tym samym czasie może być wymagane tylko jedno uwierzytelnianie klienta.|  
|HttpReceiveFailure|Wystąpił błąd podczas uzyskiwania odpowiedzi HTTP do określonego. Powiązanie punktu końcowego usługi może nie używać protokołu HTTP. Kolejną przyczyną jest fakt, że kontekst żądania HTTP został przerwany przez serwer z powodu zamknięcia usługi. Aby uzyskać więcej informacji, zobacz Dzienniki serwera.|  
|HttpRegistrationAccessDenied|Protokół HTTP nie może zarejestrować określonego adresu URL. Proces nie ma uprawnień dostępu do tej przestrzeni nazw (zobacz [rezerwacje przestrzeni nazw, rejestracje i routing,](/windows/desktop/http/namespace-reservations-registrations-and-routing) Aby uzyskać szczegółowe informacje).|  
|HttpRegistrationAlreadyExists|Protokół HTTP nie może zarejestrować określonego adresu URL. Inna aplikacja zarejestrowała już ten adres URL przy użyciu HTTP.SYS.|  
|HttpRegistrationPortInUse|Protokół HTTP nie może zarejestrować określonego adresu URL, ponieważ określony port TCP jest używany przez inną aplikację.|  
|HttpSendFailure|Wystąpił błąd podczas wykonywania żądania HTTP do określonego. Upewnij się, że przyczyna nie jest niezgodnością powiązań zabezpieczeń. Upewnij się również, że usługa nie jest skonfigurowana do SSL.|  
|MessageXmlProtocolError|Wystąpił problem z plikiem XML, który został odebrany z sieci. Zobacz wewnętrzny wyjątek, aby uzyskać więcej szczegółów.|  
|MissingContentType|Odbiorca zwrócił błąd wskazujący, że w żądaniu brakuje typu zawartości. Zobacz wewnętrzny wyjątek, aby uzyskać więcej informacji.|  
|ProxyAuthenticationLevelMismatch|Poświadczenie uwierzytelniania serwera proxy HTTP określiło wymóg wzajemnego uwierzytelniania, który jest bardziej restrykcyjny niż wymóg uwierzytelniania serwera docelowego.|  
|ProxyImpersonationLevelMismatch|Poświadczenie uwierzytelniania serwera proxy HTTP określiło ograniczenie poziomu personifikacji, które jest bardziej restrykcyjne niż ograniczenie uwierzytelniania serwera docelowego.|  
|SecureChannelFailure|Nie można nawiązać bezpiecznego kanału dla protokołu Secure Socket Layer/Transport Layer Security z określonym Urzędem.|  
|TrustFailure|Nie można nawiązać relacji zaufania dla bezpiecznego kanału Secure Socket Layer/Transport Layer Security z określonym Urzędem.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|Nie można określić jawnego adresu serwera proxy, a także UseDefaultWebProxy = true w elemencie HttpTransportBinding.|
