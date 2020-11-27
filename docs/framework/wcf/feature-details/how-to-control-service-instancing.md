---
title: 'Instrukcje: tworzenie wystąpienia usługi kontroli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: b028e062acd47118314c9fafd18dd698d04ec244
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257265"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="2caf0-102">Instrukcje: tworzenie wystąpienia usługi kontroli</span><span class="sxs-lookup"><span data-stu-id="2caf0-102">How to: Control Service Instancing</span></span>

<span data-ttu-id="2caf0-103">Ustawienie trybu wystąpienia usługi pozwala określić, kiedy <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> zostanie utworzony (i skojarzony z nim obiekt usługi zdefiniowany przez użytkownika).</span><span class="sxs-lookup"><span data-stu-id="2caf0-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="2caf0-104">Zobacz <xref:System.ServiceModel.InstanceContextMode> Wyliczenie dla możliwych trybów.</span><span class="sxs-lookup"><span data-stu-id="2caf0-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="2caf0-105">Aby uzyskać więcej informacji na temat zachowań, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="2caf0-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="2caf0-106">Aby zapoznać się z przykładami roboczymi, zobacz [Behaviors](../samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="2caf0-106">For working examples, see [Behaviors](../samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="2caf0-107">Aby sterować okresem istnienia wystąpienia usługi przy użyciu kodu</span><span class="sxs-lookup"><span data-stu-id="2caf0-107">To control the service instance lifetime using code</span></span>  
  
1. <span data-ttu-id="2caf0-108">Zastosuj <xref:System.ServiceModel.ServiceBehaviorAttribute> do klasy usługi.</span><span class="sxs-lookup"><span data-stu-id="2caf0-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2. <span data-ttu-id="2caf0-109">Ustaw <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> Właściwość na jedną z następujących wartości: <xref:System.ServiceModel.InstanceContextMode.PerCall> , <xref:System.ServiceModel.InstanceContextMode.PerSession> , lub <xref:System.ServiceModel.InstanceContextMode.Single> .</span><span class="sxs-lookup"><span data-stu-id="2caf0-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="2caf0-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="2caf0-110">Example</span></span>  

 <span data-ttu-id="2caf0-111">Poniższy przykład kodu ustawia <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> Właściwość <xref:System.ServiceModel.ServiceBehaviorAttribute> atrybutu na <xref:System.ServiceModel.InstanceContextMode.PerCall> .</span><span class="sxs-lookup"><span data-stu-id="2caf0-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2caf0-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2caf0-112">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="2caf0-113">Usługa: Przykłady zachowań</span><span class="sxs-lookup"><span data-stu-id="2caf0-113">Service: Behaviors Samples</span></span>](../samples/behaviors.md)
