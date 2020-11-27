---
title: Tworzenie usług międzyoperacyjnych 1.1 profilu podstawowego WS-I
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: b5d262c3e0443503ccbf49a1a468c82843799a61
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255055"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="c3f4b-102">Tworzenie usług międzyoperacyjnych 1.1 profilu podstawowego WS-I</span><span class="sxs-lookup"><span data-stu-id="c3f4b-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>

<span data-ttu-id="c3f4b-103">Aby skonfigurować punkt końcowy usługi WCF do współdziałania z klientami usługi sieci Web ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="c3f4b-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="c3f4b-104">Użyj <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> typu jako typu powiązania dla punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="c3f4b-105">Nie używaj funkcji wywołania zwrotnego i kontraktu sesji ani zachowań transakcji w punkcie końcowym usługi</span><span class="sxs-lookup"><span data-stu-id="c3f4b-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
<span data-ttu-id="c3f4b-106">Opcjonalnie można włączyć obsługę uwierzytelniania przy użyciu protokołu HTTPS i klienta na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
<span data-ttu-id="c3f4b-107">Następujące funkcje <xref:System.ServiceModel.BasicHttpBinding> klasy wymagają funkcjonalności poza WS-I Basic Profile 1,1:</span><span class="sxs-lookup"><span data-stu-id="c3f4b-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="c3f4b-108">Kodowanie komunikatów mechanizmu optymalizacji transmisji wiadomości (MTOM) kontrolowane przez <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c3f4b-109">Pozostaw tę właściwość jako wartość domyślną, która <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> nie używa mechanizmu MTOM.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="c3f4b-110">Zabezpieczenia komunikatów kontrolowane przez <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> wartość zapewniają obsługę WS-Security zgodności z profilem zabezpieczeń WS-I Basic 1,0.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="c3f4b-111">Pozostaw tę właściwość domyślną wartością, która <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> nie jest używana w usłudze WS-Security.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
<span data-ttu-id="c3f4b-112">Aby uzyskać dostęp do metadanych usługi WCF ASP.NET, użyj narzędzia do generowania klienta usługi sieci Web: narzędzia do [Web Services Description Language (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Narzędzia odnajdywania usług sieci Web (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))i funkcji **Dodaj odwołanie sieci Web** w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Web Services Discovery Tool (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100)), and the **Add Web Reference** feature in Visual Studio.</span></span> <span data-ttu-id="c3f4b-113">Włącz publikację metadanych.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-113">Enable metadata publication.</span></span> <span data-ttu-id="c3f4b-114">Aby uzyskać więcej informacji, zobacz [Publikowanie punktów końcowych metadanych](publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="c3f4b-114">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3f4b-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="c3f4b-115">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c3f4b-116">Opis</span><span class="sxs-lookup"><span data-stu-id="c3f4b-116">Description</span></span>  

 <span data-ttu-id="c3f4b-117">Poniższy przykładowy kod pokazuje, jak dodać punkt końcowy WCF, który jest zgodny z klientami usługi sieci Web ASP.NET w kodzie i, Alternatywnie, w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c3f4b-117">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c3f4b-118">Kod</span><span class="sxs-lookup"><span data-stu-id="c3f4b-118">Code</span></span>  

 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c3f4b-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c3f4b-119">See also</span></span>

- [<span data-ttu-id="c3f4b-120">Współdziałanie z usługami ASP.NET w sieci Web</span><span class="sxs-lookup"><span data-stu-id="c3f4b-120">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
