---
title: 'Instrukcje: sprawdzanie lub modyfikowanie parametrów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: e8b2674d8efc0ef3ac2f1dd6ab0df559195c274c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249036"
---
# <a name="how-to-inspect-or-modify-parameters"></a>Instrukcje: sprawdzanie lub modyfikowanie parametrów

Możesz sprawdzić lub zmodyfikować przychodzące lub wychodzące komunikaty dla pojedynczej operacji na obiekcie klienta Windows Communication Foundation (WCF) lub w usłudze WCF, implementując <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interfejs i wstawiając go do środowiska uruchomieniowego klienta lub usługi. Zwykle zachowanie operacji służy do dodawania inspektorów parametrów dla jednej operacji; Inne zachowania mogą służyć do zapewnienia łatwego dostępu do środowiska uruchomieniowego w większym zakresie. Aby uzyskać więcej informacji, zobacz [Rozszerzanie klientów](extending-clients.md) i [rozszerzanie dyspozytorów](extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Inspekcja lub modyfikowanie parametrów  
  
1. Zaimplementuj interfejs <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2. Zaimplementuj <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType> , <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> , <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> lub <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (w zależności od wymaganego zakresu), aby dodać Inspektor parametrów do <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> właściwości lub.  
  
3. Wstaw zachowanie przed wywołaniem <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> lub <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> metodą w <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> . Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu pokazuje, w kolejności:  
  
- Implementacja inspektora parametrów.  
  
- Implementacja zachowania, która wstawia Inspektor parametrów przy użyciu <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType> , <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> i <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> .  
  
- Plik konfiguracji, który ładuje i uruchamia zachowanie punktu końcowego w aplikacji klienckiej w celu wstawienia inspektora parametrów na kliencie.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md)
