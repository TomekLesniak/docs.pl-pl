---
title: Niezabezpieczony klient internetowy i usługa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 017744d692d6fd4183fde3c21e71fcee2f35844e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535361"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="feaa9-102">Niezabezpieczony klient internetowy i usługa</span><span class="sxs-lookup"><span data-stu-id="feaa9-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="feaa9-103">Na poniższej ilustracji przedstawiono przykład publicznego, niezabezpieczonego Windows Communication Foundation (WCF) i usługi:</span><span class="sxs-lookup"><span data-stu-id="feaa9-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Zrzut ekranu przedstawiający niezabezpieczony scenariusz internetowy](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="feaa9-105">Charakterystyka</span><span class="sxs-lookup"><span data-stu-id="feaa9-105">Characteristic</span></span>|<span data-ttu-id="feaa9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="feaa9-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="feaa9-107">Tryb zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="feaa9-107">Security Mode</span></span>|<span data-ttu-id="feaa9-108">Brak</span><span class="sxs-lookup"><span data-stu-id="feaa9-108">None</span></span>|  
|<span data-ttu-id="feaa9-109">Transport</span><span class="sxs-lookup"><span data-stu-id="feaa9-109">Transport</span></span>|<span data-ttu-id="feaa9-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="feaa9-110">HTTP</span></span>|  
|<span data-ttu-id="feaa9-111">Wiązanie</span><span class="sxs-lookup"><span data-stu-id="feaa9-111">Binding</span></span>|<span data-ttu-id="feaa9-112"><xref:System.ServiceModel.BasicHttpBinding> w kodzie lub w [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) elemencie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="feaa9-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="feaa9-113">Współdziałanie</span><span class="sxs-lookup"><span data-stu-id="feaa9-113">Interoperability</span></span>|<span data-ttu-id="feaa9-114">Z istniejącymi usługami i klientami usług sieci Web</span><span class="sxs-lookup"><span data-stu-id="feaa9-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="feaa9-115">Authentication</span><span class="sxs-lookup"><span data-stu-id="feaa9-115">Authentication</span></span>|<span data-ttu-id="feaa9-116">Brak</span><span class="sxs-lookup"><span data-stu-id="feaa9-116">None</span></span>|  
|<span data-ttu-id="feaa9-117">Integralność</span><span class="sxs-lookup"><span data-stu-id="feaa9-117">Integrity</span></span>|<span data-ttu-id="feaa9-118">Brak</span><span class="sxs-lookup"><span data-stu-id="feaa9-118">None</span></span>|  
|<span data-ttu-id="feaa9-119">Poufność</span><span class="sxs-lookup"><span data-stu-id="feaa9-119">Confidentiality</span></span>|<span data-ttu-id="feaa9-120">Brak</span><span class="sxs-lookup"><span data-stu-id="feaa9-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="feaa9-121">Usługa</span><span class="sxs-lookup"><span data-stu-id="feaa9-121">Service</span></span>  
 <span data-ttu-id="feaa9-122">Poniższy kod i konfiguracja są przeznaczone do niezależnego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="feaa9-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="feaa9-123">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="feaa9-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="feaa9-124">Tworzenie usługi autonomicznej przy użyciu kodu bez konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="feaa9-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="feaa9-125">Utwórz usługę przy użyciu podanej konfiguracji, ale nie Definiuj żadnych punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="feaa9-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="feaa9-126">Kod</span><span class="sxs-lookup"><span data-stu-id="feaa9-126">Code</span></span>  
 <span data-ttu-id="feaa9-127">Poniższy kod pokazuje, jak utworzyć punkt końcowy bez zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="feaa9-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="feaa9-128">Domyślnie <xref:System.ServiceModel.BasicHttpBinding> ma tryb zabezpieczeń ustawiony na <xref:System.ServiceModel.BasicHttpSecurityMode.None> .</span><span class="sxs-lookup"><span data-stu-id="feaa9-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="feaa9-129">Konfiguracja usługi</span><span class="sxs-lookup"><span data-stu-id="feaa9-129">Service Configuration</span></span>  
 <span data-ttu-id="feaa9-130">Poniższy kod konfiguruje ten sam punkt końcowy przy użyciu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="feaa9-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="feaa9-131">Klient</span><span class="sxs-lookup"><span data-stu-id="feaa9-131">Client</span></span>  
 <span data-ttu-id="feaa9-132">Poniższy kod i konfiguracja są przeznaczone do niezależnego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="feaa9-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="feaa9-133">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="feaa9-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="feaa9-134">Utwórz klienta autonomicznego przy użyciu kodu (i kodu klienta).</span><span class="sxs-lookup"><span data-stu-id="feaa9-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="feaa9-135">Utwórz klienta, który nie definiuje żadnych adresów punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="feaa9-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="feaa9-136">Zamiast tego należy użyć konstruktora klienta, który przyjmuje nazwę konfiguracji jako argument.</span><span class="sxs-lookup"><span data-stu-id="feaa9-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="feaa9-137">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="feaa9-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="feaa9-138">Kod</span><span class="sxs-lookup"><span data-stu-id="feaa9-138">Code</span></span>  
 <span data-ttu-id="feaa9-139">Poniższy kod przedstawia podstawowy klient WCF, który uzyskuje dostęp do niezabezpieczonego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="feaa9-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="feaa9-140">Konfiguracja klienta</span><span class="sxs-lookup"><span data-stu-id="feaa9-140">Client Configuration</span></span>  
 <span data-ttu-id="feaa9-141">Poniższy kod konfiguruje klienta.</span><span class="sxs-lookup"><span data-stu-id="feaa9-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="feaa9-142">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="feaa9-142">See also</span></span>

- [<span data-ttu-id="feaa9-143">Typowe scenariusze zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="feaa9-143">Common Security Scenarios</span></span>](common-security-scenarios.md)
- [<span data-ttu-id="feaa9-144">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="feaa9-144">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="feaa9-145">[Model zabezpieczeń dla sieci szkieletowej aplikacji systemu Windows Server](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="feaa9-145">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
