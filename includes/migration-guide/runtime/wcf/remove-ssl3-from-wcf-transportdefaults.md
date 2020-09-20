---
ms.openlocfilehash: a5f4047d70276a90c9d72918a2559fd795feb26e
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770932"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="d34e7-101">Usuń Ssl3 z TransportDefaults WCF</span><span class="sxs-lookup"><span data-stu-id="d34e7-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="d34e7-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d34e7-102">Details</span></span>

<span data-ttu-id="d34e7-103">W przypadku korzystania z programu NetTcp z zabezpieczeniami transportu i typem poświadczeń certyfikatu protokół SSL 3 nie jest już domyślnym protokołem używanym do negocjowania bezpiecznego połączenia.</span><span class="sxs-lookup"><span data-stu-id="d34e7-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="d34e7-104">W większości przypadków nie powinno się mieć wpływu na istniejące aplikacje, ponieważ protokół TLS 1,0 został zawsze uwzględniony na liście protokołów dla NetTcp.</span><span class="sxs-lookup"><span data-stu-id="d34e7-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="d34e7-105">Wszyscy istniejący klienci powinni mieć możliwość negocjowania połączenia przy użyciu co najmniej protokołu TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="d34e7-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d34e7-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d34e7-106">Suggestion</span></span>

<span data-ttu-id="d34e7-107">Jeśli Ssl3 jest wymagany, użyj jednego z poniższych mechanizmów konfiguracyjnych, aby dodać Ssl3 do listy protokołów negocjowanych.</span><span class="sxs-lookup"><span data-stu-id="d34e7-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>
- [<span data-ttu-id="d34e7-108">\<transport> z \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d34e7-108">\<transport> of \<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)
- [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)

| <span data-ttu-id="d34e7-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d34e7-109">Name</span></span>    | <span data-ttu-id="d34e7-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="d34e7-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="d34e7-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="d34e7-111">Scope</span></span>   | <span data-ttu-id="d34e7-112">Edge</span><span class="sxs-lookup"><span data-stu-id="d34e7-112">Edge</span></span>    |
| <span data-ttu-id="d34e7-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="d34e7-113">Version</span></span> | <span data-ttu-id="d34e7-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d34e7-114">4.6.2</span></span>   |
| <span data-ttu-id="d34e7-115">Typ</span><span class="sxs-lookup"><span data-stu-id="d34e7-115">Type</span></span>    | <span data-ttu-id="d34e7-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d34e7-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d34e7-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d34e7-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
