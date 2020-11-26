---
title: 'Instrukcje: sprawdzanie i modyfikowanie komunikatów w usłudze'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 8d1ce6ef00462adb38e3d59c3d9bd35694c4dbe9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249062"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Instrukcje: sprawdzanie i modyfikowanie komunikatów w usłudze

Możesz sprawdzić lub zmodyfikować komunikaty przychodzące lub wychodzące dla klienta Windows Communication Foundation (WCF), implementując <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> i wstawiając go do środowiska uruchomieniowego usługi. Aby uzyskać więcej informacji, zobacz [rozszerzanie dyspozytorów](extending-dispatchers.md). Równoważna funkcja w usłudze to <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> .  
  
### <a name="to-inspect-or-modify-messages"></a>Aby sprawdzić lub zmodyfikować komunikaty  
  
1. Zaimplementuj interfejs <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.  
  
2. Zaimplementuj <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> interfejs, lub, <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> w zależności od zakresu, w którym chcesz łatwo wstawić inspektora komunikatów usługi.  
  
3. Wstaw zachowanie przed wywołaniem <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> metody na <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> . Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu pokazuje, w kolejności:  
  
- Implementacja inspektora usługi.  
  
- Zachowanie usługi, które wstawia inspektora.  
  
- Plik konfiguracji, który ładuje i uruchamia zachowanie w aplikacji usługi.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md)
