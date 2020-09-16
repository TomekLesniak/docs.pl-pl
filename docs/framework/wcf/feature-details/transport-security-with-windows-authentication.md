---
title: Zabezpieczenia transportu z uwierzytelnianiem systemu Windows
description: Zapoznaj się z tym scenariuszem, który pokazuje klient lub usługę WCF zabezpieczone przez zabezpieczenia systemu Windows. W tym przykładzie usługa intranetowa wyświetla informacje o zasobach ludzkich.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 9b81f2f2fb6352af254146951ed35ad4fdca8caa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545210"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="0f60a-104">Zabezpieczenia transportu z uwierzytelnianiem systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0f60a-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="0f60a-105">W poniższym scenariuszu przedstawiono klienta i usługę Windows Communication Foundation (WCF) zabezpieczony przez zabezpieczenia systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0f60a-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="0f60a-106">Aby uzyskać więcej informacji na temat programowania, zobacz [How to: Zabezpieczanie usługi przy użyciu poświadczeń systemu Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="0f60a-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="0f60a-107">Intranetowa usługa sieci Web Wyświetla informacje o zasobach ludzkich.</span><span class="sxs-lookup"><span data-stu-id="0f60a-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="0f60a-108">Klient jest aplikacją formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0f60a-108">The client is a Windows Form application.</span></span> <span data-ttu-id="0f60a-109">Aplikacja jest wdrażana w domenie z kontrolerem Kerberos zabezpieczania domeny.</span><span class="sxs-lookup"><span data-stu-id="0f60a-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Zabezpieczenia transportu z uwierzytelnianiem systemu Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="0f60a-111">Charakterystyka</span><span class="sxs-lookup"><span data-stu-id="0f60a-111">Characteristic</span></span>|<span data-ttu-id="0f60a-112">Opis</span><span class="sxs-lookup"><span data-stu-id="0f60a-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0f60a-113">Tryb zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="0f60a-113">Security Mode</span></span>|<span data-ttu-id="0f60a-114">Transport</span><span class="sxs-lookup"><span data-stu-id="0f60a-114">Transport</span></span>|  
|<span data-ttu-id="0f60a-115">Współdziałanie</span><span class="sxs-lookup"><span data-stu-id="0f60a-115">Interoperability</span></span>|<span data-ttu-id="0f60a-116">Tylko WCF</span><span class="sxs-lookup"><span data-stu-id="0f60a-116">WCF only</span></span>|  
|<span data-ttu-id="0f60a-117">Uwierzytelnianie (serwer)</span><span class="sxs-lookup"><span data-stu-id="0f60a-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="0f60a-118">Uwierzytelnianie (klient)</span><span class="sxs-lookup"><span data-stu-id="0f60a-118">Authentication (Client)</span></span>|<span data-ttu-id="0f60a-119">Tak (przy użyciu zintegrowanego uwierzytelniania systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="0f60a-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="0f60a-120">Tak (przy użyciu zintegrowanego uwierzytelniania systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="0f60a-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="0f60a-121">Integralność</span><span class="sxs-lookup"><span data-stu-id="0f60a-121">Integrity</span></span>|<span data-ttu-id="0f60a-122">Yes</span><span class="sxs-lookup"><span data-stu-id="0f60a-122">Yes</span></span>|  
|<span data-ttu-id="0f60a-123">Poufność</span><span class="sxs-lookup"><span data-stu-id="0f60a-123">Confidentiality</span></span>|<span data-ttu-id="0f60a-124">Yes</span><span class="sxs-lookup"><span data-stu-id="0f60a-124">Yes</span></span>|  
|<span data-ttu-id="0f60a-125">Transport</span><span class="sxs-lookup"><span data-stu-id="0f60a-125">Transport</span></span>|<span data-ttu-id="0f60a-126">Waga. PROTOKOŁ</span><span class="sxs-lookup"><span data-stu-id="0f60a-126">NET.TCP</span></span>|  
|<span data-ttu-id="0f60a-127">Wiązanie</span><span class="sxs-lookup"><span data-stu-id="0f60a-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="0f60a-128">Usługa</span><span class="sxs-lookup"><span data-stu-id="0f60a-128">Service</span></span>  
 <span data-ttu-id="0f60a-129">Poniższy kod i konfiguracja są przeznaczone do niezależnego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="0f60a-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0f60a-130">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="0f60a-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="0f60a-131">Tworzenie usługi autonomicznej przy użyciu kodu bez konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0f60a-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="0f60a-132">Utwórz usługę przy użyciu podanej konfiguracji, ale nie Definiuj żadnych punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="0f60a-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0f60a-133">Kod</span><span class="sxs-lookup"><span data-stu-id="0f60a-133">Code</span></span>  
 <span data-ttu-id="0f60a-134">Poniższy kod przedstawia sposób tworzenia punktu końcowego usługi, który korzysta z zabezpieczeń systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0f60a-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="0f60a-135">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="0f60a-135">Configuration</span></span>  
 <span data-ttu-id="0f60a-136">Aby skonfigurować punkt końcowy usługi, można użyć następującej konfiguracji zamiast kodu:</span><span class="sxs-lookup"><span data-stu-id="0f60a-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="0f60a-137">Klient</span><span class="sxs-lookup"><span data-stu-id="0f60a-137">Client</span></span>  
 <span data-ttu-id="0f60a-138">Poniższy kod i konfiguracja są przeznaczone do niezależnego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="0f60a-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0f60a-139">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="0f60a-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="0f60a-140">Utwórz klienta autonomicznego przy użyciu kodu (i kodu klienta).</span><span class="sxs-lookup"><span data-stu-id="0f60a-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="0f60a-141">Utwórz klienta, który nie definiuje żadnych adresów punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="0f60a-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0f60a-142">Zamiast tego należy użyć konstruktora klienta, który przyjmuje nazwę konfiguracji jako argument.</span><span class="sxs-lookup"><span data-stu-id="0f60a-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0f60a-143">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="0f60a-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="0f60a-144">Kod</span><span class="sxs-lookup"><span data-stu-id="0f60a-144">Code</span></span>  
 <span data-ttu-id="0f60a-145">Poniższy kod tworzy klienta.</span><span class="sxs-lookup"><span data-stu-id="0f60a-145">The following code creates the client.</span></span> <span data-ttu-id="0f60a-146">Powiązanie jest skonfigurowane do korzystania z zabezpieczeń trybu transportu przy użyciu transportu TCP z typem poświadczeń klienta ustawionym na Windows.</span><span class="sxs-lookup"><span data-stu-id="0f60a-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="0f60a-147">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="0f60a-147">Configuration</span></span>  
 <span data-ttu-id="0f60a-148">W celu utworzenia klienta można użyć poniższej konfiguracji zamiast kodu.</span><span class="sxs-lookup"><span data-stu-id="0f60a-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f60a-149">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0f60a-149">See also</span></span>

- [<span data-ttu-id="0f60a-150">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="0f60a-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="0f60a-151">Instrukcje: Zabezpieczanie usługi za pomocą poświadczeń systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0f60a-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="0f60a-152">[Model zabezpieczeń dla sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0f60a-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
