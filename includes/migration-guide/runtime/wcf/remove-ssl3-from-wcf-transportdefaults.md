---
ms.openlocfilehash: 23987c300ac4fbad401de180b63106cd234f8d27
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497150"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Usuń Ssl3 z TransportDefaults WCF

#### <a name="details"></a>Szczegóły

W przypadku korzystania z programu NetTcp z zabezpieczeniami transportu i typem poświadczeń certyfikatu protokół SSL 3 nie jest już domyślnym protokołem używanym do negocjowania bezpiecznego połączenia. W większości przypadków nie powinno się mieć wpływu na istniejące aplikacje, ponieważ protokół TLS 1,0 został zawsze uwzględniony na liście protokołów dla NetTcp. Wszyscy istniejący klienci powinni mieć możliwość negocjowania połączenia przy użyciu co najmniej protokołu TLS 1.0.

#### <a name="suggestion"></a>Sugestia

Jeśli Ssl3 jest wymagany, użyj jednego z poniższych mechanizmów konfiguracyjnych, aby dodać Ssl3 do listy protokołów negocjowanych.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[ &lt; sslStreamSecurity &gt; sekcja elementu &lt; CustomBinding &gt; ] ~/docs/Framework/Configure-Apps/File-Schema/WCF/sslStreamSecurity.MD)</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
