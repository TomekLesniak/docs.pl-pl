---
title: 'Instrukcje: eksportowanie metadanych z punktów końcowych usług'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: c253358b68cf18a23bab4d12d4ad760874103bff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246410"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="a61b2-102">Instrukcje: eksportowanie metadanych z punktów końcowych usług</span><span class="sxs-lookup"><span data-stu-id="a61b2-102">How to: Export Metadata from Service Endpoints</span></span>

<span data-ttu-id="a61b2-103">W tym temacie wyjaśniono, jak eksportować metadane z punktów końcowych usługi.</span><span class="sxs-lookup"><span data-stu-id="a61b2-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="a61b2-104">Aby wyeksportować metadane z punktów końcowych usługi</span><span class="sxs-lookup"><span data-stu-id="a61b2-104">To export metadata from service endpoints</span></span>  
  
1. <span data-ttu-id="a61b2-105">Utwórz nowy projekt aplikacji konsoli programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a61b2-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="a61b2-106">Dodaj kod przedstawiony w poniższych krokach w wygenerowanym pliku Program.cs w ramach metody Main ().</span><span class="sxs-lookup"><span data-stu-id="a61b2-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2. <span data-ttu-id="a61b2-107">Utwórz <xref:System.ServiceModel.Description.WsdlExporter> .</span><span class="sxs-lookup"><span data-stu-id="a61b2-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. <span data-ttu-id="a61b2-108">Ustaw <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> Właściwość na jedną z wartości w <xref:System.ServiceModel.Description.PolicyVersion> wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="a61b2-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="a61b2-109">Ten przykład ustawia wartość <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> odpowiadającą WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="a61b2-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. <span data-ttu-id="a61b2-110">Utwórz tablicę <xref:System.ServiceModel.Description.ServiceEndpoint> obiektów.</span><span class="sxs-lookup"><span data-stu-id="a61b2-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. <span data-ttu-id="a61b2-111">Eksportuj metadane dla każdego punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="a61b2-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. <span data-ttu-id="a61b2-112">Zaznacz, aby upewnić się, że podczas procesu eksportowania nie wystąpiły żadne błędy i Pobierz metadane.</span><span class="sxs-lookup"><span data-stu-id="a61b2-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. <span data-ttu-id="a61b2-113">Teraz można użyć metadanych, takich jak zapis do pliku przez wywołanie <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> metody.</span><span class="sxs-lookup"><span data-stu-id="a61b2-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a61b2-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="a61b2-114">Example</span></span>  

 <span data-ttu-id="a61b2-115">Poniżej znajduje się pełna lista kodów dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="a61b2-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a61b2-116">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="a61b2-116">Compiling the Code</span></span>  

 <span data-ttu-id="a61b2-117">Podczas kompilowania System.ServiceModel.dll odwołania do Program.cs.</span><span class="sxs-lookup"><span data-stu-id="a61b2-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61b2-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a61b2-118">See also</span></span>

- [<span data-ttu-id="a61b2-119">Przegląd architektury metadanych</span><span class="sxs-lookup"><span data-stu-id="a61b2-119">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="a61b2-120">Używanie metadanych</span><span class="sxs-lookup"><span data-stu-id="a61b2-120">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="a61b2-121">Punkty końcowe: adresy, wiązania i kontrakty</span><span class="sxs-lookup"><span data-stu-id="a61b2-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
