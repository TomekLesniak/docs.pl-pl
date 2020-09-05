---
ms.openlocfilehash: afcb9b950d4c47b4251dcc8ab0cf9cfc702005c8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497752"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="dcd3e-101">Usługi WCF korzystające z NETTCP z zabezpieczeniami SSL i uwierzytelnianiem certyfikatu MD5</span><span class="sxs-lookup"><span data-stu-id="dcd3e-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="dcd3e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="dcd3e-102">Details</span></span>

<span data-ttu-id="dcd3e-103">.NET Framework 4,6 dodaje protokoły TLS 1,1 i TLS 1,2 do listy domyślnych protokołów protokołu SSL WCF.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="dcd3e-104">Gdy komputery klienckie i serwery mają zainstalowany .NET Framework 4,6 lub nowszy, protokół TLS 1,2 jest używany do negocjacji. Protokół TLS 1,2 nie obsługuje uwierzytelniania certyfikatów MD5.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="dcd3e-105">W związku z tym, jeśli klient korzysta z certyfikatu MD5, klient programu WCF nie będzie mógł nawiązać połączenia z usługą WCF.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dcd3e-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="dcd3e-106">Suggestion</span></span>

<span data-ttu-id="dcd3e-107">Ten problem można obejść, aby klient programu WCF mógł połączyć się z serwerem WCF, wykonując jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="dcd3e-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="dcd3e-108">Zaktualizuj certyfikat, aby nie używał algorytmu MD5.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="dcd3e-109">Jest to zalecane rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-109">This is the recommended solution.</span></span>
- <span data-ttu-id="dcd3e-110">Jeśli powiązanie nie jest konfigurowane dynamicznie w kodzie źródłowym, zaktualizuj plik konfiguracji aplikacji tak, aby korzystał z protokołu TLS 1,1 lub starszej wersji.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="dcd3e-111">Dzięki temu można nadal używać certyfikatu z algorytmem wyznaczania wartości skrótu MD5.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="dcd3e-112">To obejście nie jest zalecane, ponieważ certyfikat z algorytmem wyznaczania wartości skrótu MD5 jest uznawany za niezabezpieczony.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="dcd3e-113">Następujący plik konfiguracji wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="dcd3e-113">The following configuration file does this:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- <span data-ttu-id="dcd3e-114">Jeśli powiązanie jest konfigurowane dynamicznie w kodzie źródłowym, zaktualizuj właściwość tak, <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> aby używała protokołu TLS 1,1 ( <xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> lub starszej wersji protokołu w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="dcd3e-115">To obejście nie jest zalecane, ponieważ certyfikat z algorytmem wyznaczania wartości skrótu MD5 jest uznawany za niezabezpieczony.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="dcd3e-116">Nazwa</span><span class="sxs-lookup"><span data-stu-id="dcd3e-116">Name</span></span>    | <span data-ttu-id="dcd3e-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="dcd3e-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="dcd3e-118">Zakres</span><span class="sxs-lookup"><span data-stu-id="dcd3e-118">Scope</span></span>   | <span data-ttu-id="dcd3e-119">Mały</span><span class="sxs-lookup"><span data-stu-id="dcd3e-119">Minor</span></span>   |
| <span data-ttu-id="dcd3e-120">Wersja</span><span class="sxs-lookup"><span data-stu-id="dcd3e-120">Version</span></span> | <span data-ttu-id="dcd3e-121">4,6</span><span class="sxs-lookup"><span data-stu-id="dcd3e-121">4.6</span></span>     |
| <span data-ttu-id="dcd3e-122">Typ</span><span class="sxs-lookup"><span data-stu-id="dcd3e-122">Type</span></span>    | <span data-ttu-id="dcd3e-123">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="dcd3e-123">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="dcd3e-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="dcd3e-124">Affected APIs</span></span>

<span data-ttu-id="dcd3e-125">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="dcd3e-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
