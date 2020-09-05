---
ms.openlocfilehash: 23987c300ac4fbad401de180b63106cd234f8d27
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497150"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="2218e-101">Usuń Ssl3 z TransportDefaults WCF</span><span class="sxs-lookup"><span data-stu-id="2218e-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="2218e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2218e-102">Details</span></span>

<span data-ttu-id="2218e-103">W przypadku korzystania z programu NetTcp z zabezpieczeniami transportu i typem poświadczeń certyfikatu protokół SSL 3 nie jest już domyślnym protokołem używanym do negocjowania bezpiecznego połączenia.</span><span class="sxs-lookup"><span data-stu-id="2218e-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="2218e-104">W większości przypadków nie powinno się mieć wpływu na istniejące aplikacje, ponieważ protokół TLS 1,0 został zawsze uwzględniony na liście protokołów dla NetTcp.</span><span class="sxs-lookup"><span data-stu-id="2218e-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="2218e-105">Wszyscy istniejący klienci powinni mieć możliwość negocjowania połączenia przy użyciu co najmniej protokołu TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="2218e-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2218e-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="2218e-106">Suggestion</span></span>

<span data-ttu-id="2218e-107">Jeśli Ssl3 jest wymagany, użyj jednego z poniższych mechanizmów konfiguracyjnych, aby dodać Ssl3 do listy protokołów negocjowanych.</span><span class="sxs-lookup"><span data-stu-id="2218e-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="2218e-108">[ &lt; sslStreamSecurity &gt; sekcja elementu &lt; CustomBinding &gt; ] ~/docs/Framework/Configure-Apps/File-Schema/WCF/sslStreamSecurity.MD)</span><span class="sxs-lookup"><span data-stu-id="2218e-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="2218e-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2218e-109">Name</span></span>    | <span data-ttu-id="2218e-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="2218e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2218e-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="2218e-111">Scope</span></span>   |<span data-ttu-id="2218e-112">Edge</span><span class="sxs-lookup"><span data-stu-id="2218e-112">Edge</span></span>|
|<span data-ttu-id="2218e-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="2218e-113">Version</span></span>|<span data-ttu-id="2218e-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2218e-114">4.6.2</span></span>|
|<span data-ttu-id="2218e-115">Typ</span><span class="sxs-lookup"><span data-stu-id="2218e-115">Type</span></span>|<span data-ttu-id="2218e-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="2218e-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2218e-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2218e-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
