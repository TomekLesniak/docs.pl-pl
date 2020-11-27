---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2be32591c4844cc6d5d0f02916dd1563bb15dc2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288791"
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement

HttpTransportBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa HttpTransportBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa HttpTransportBindingElement ma następujące właściwości:  
  
### <a name="allowcookies"></a>AllowCookies  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy klient akceptuje pliki cookie i propaguje je do przyszłych żądań.  
  
### <a name="authenticationscheme"></a>AuthenticationScheme  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Schemat uwierzytelniania używany do uwierzytelniania żądań klientów przetwarzanych przez odbiornik HTTP.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy serwery proxy są ignorowane dla adresów lokalnych.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Po włączeniu połączenia HTTP są utrzymywane bez względu na poziom aktywności.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar puli buforów.  
  
### <a name="proxyaddress"></a>ProxyAddress  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator URI, który zawiera adres serwera proxy do użycia w żądaniach HTTP.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Schemat uwierzytelniania używany do uwierzytelniania żądań klientów przetwarzanych przez serwer proxy HTTP.  
  
### <a name="realm"></a>Obszar  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Obszar uwierzytelniania.  
  
### <a name="transfermode"></a>Elementy TransferMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość określająca, czy komunikaty są buforowane, czy przesyłane strumieniowo, czy też żądanie lub odpowiedź.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy na serwerze jest włączona funkcja udostępniania niebezpiecznego połączenia.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy ustawienia serwera proxy dla całego komputera są używane zamiast ustawień określonych przez użytkownika.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
