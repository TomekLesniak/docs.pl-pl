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
# <a name="how-to-export-metadata-from-service-endpoints"></a>Instrukcje: eksportowanie metadanych z punktów końcowych usług

W tym temacie wyjaśniono, jak eksportować metadane z punktów końcowych usługi.  
  
### <a name="to-export-metadata-from-service-endpoints"></a>Aby wyeksportować metadane z punktów końcowych usługi  
  
1. Utwórz nowy projekt aplikacji konsoli programu Visual Studio. Dodaj kod przedstawiony w poniższych krokach w wygenerowanym pliku Program.cs w ramach metody Main ().  
  
2. Utwórz <xref:System.ServiceModel.Description.WsdlExporter> .  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. Ustaw <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> Właściwość na jedną z wartości w <xref:System.ServiceModel.Description.PolicyVersion> wyliczeniu. Ten przykład ustawia wartość <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> odpowiadającą WS-Policy 1,5.  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. Utwórz tablicę <xref:System.ServiceModel.Description.ServiceEndpoint> obiektów.  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. Eksportuj metadane dla każdego punktu końcowego usługi.  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. Zaznacz, aby upewnić się, że podczas procesu eksportowania nie wystąpiły żadne błędy i Pobierz metadane.  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. Teraz można użyć metadanych, takich jak zapis do pliku przez wywołanie <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> metody.  
  
## <a name="example"></a>Przykład  

 Poniżej znajduje się pełna lista kodów dla tego przykładu.  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Podczas kompilowania System.ServiceModel.dll odwołania do Program.cs.  
  
## <a name="see-also"></a>Zobacz też

- [Przegląd architektury metadanych](metadata-architecture-overview.md)
- [Używanie metadanych](using-metadata.md)
- [Punkty końcowe: adresy, wiązania i kontrakty](endpoints-addresses-bindings-and-contracts.md)
