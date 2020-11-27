---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: eecf2b0bf459fd14236c550e393149553183b3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267926"
---
# <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings

LocalServiceSecuritySettings  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa LocalServiceSecuritySettings nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa LocalServiceSecuritySettings ma następujące właściwości:  
  
### <a name="detectreplays"></a>Włączonej opcji DetectReplays  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy ataki powtarzające się na kanał są wykrywane i rozwiązywane automatycznie.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba oczekujących sesji bezpieczeństwa obsługiwanych przez usługę.  
  
### <a name="issuedcookielifetime"></a>IssuedCookieLifetime  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan określający okres istnienia wystawiony dla wszystkich nowych plików cookie zabezpieczeń.  
  
### <a name="maxcachedcookies"></a>MaxCachedCookies  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba plików cookie, które mogą być buforowane.  
  
### <a name="maxclockskew"></a>MaxClockSkew  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan określający maksymalną różnicę czasu między zegarami systemowymi dwóch osób komunikujących się.  
  
### <a name="maxpendingsessions"></a>MaxPendingSessions  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba oczekujących połączeń w usłudze.  
  
### <a name="maxstatefulnegotiations"></a>MaxStatefulNegotiations  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba negocjacji zabezpieczeń, które mogą być jednocześnie aktywne.  
  
### <a name="negotiationtimeout"></a>NegotiationTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan, który określa maksymalny czas trwania fazy negocjowania zabezpieczeń między serwerem a klientem.  
  
### <a name="reconnecttransportonfailure"></a>ReconnectTransportOnFailure  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy połączenia przy użyciu funkcji WS-Reliable Messaging próbują ponownie nawiązać połączenie po wystąpieniu błędów transportu.  
  
### <a name="replaycachesize"></a>ReplayCacheSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba buforowanych identyfikatorów jednorazowych używanych do wykrywania powtórzeń.  
  
### <a name="replaywindow"></a>ReplayWindow  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan określający czas, w którym identyfikatorów jednorazowych poszczególnych komunikatów są prawidłowe.  
  
### <a name="sessionkeyrenewalinterval"></a>SessionKeyRenewalInterval  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan, który określa czas, po którym inicjator odnawia klucz dla sesji zabezpieczeń.  
  
### <a name="sessionkeyrolloverinterval"></a>SessionKeyRolloverInterval  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan, który określa przedział czasu, w którym poprzedni klucz sesji jest ważny w przypadku komunikatów przychodzących podczas odnawiania klucza.  
  
### <a name="timestampvalidityduration"></a>TimestampValidityDuration  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan określający czas, w którym sygnatura czasowa jest prawidłowa.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
