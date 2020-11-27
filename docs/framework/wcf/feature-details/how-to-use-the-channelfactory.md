---
title: 'Instrukcje: używanie elementu ChannelFactory'
description: Dowiedz się, jak utworzyć fabrykę kanałów, aby utworzyć więcej niż jeden kanał na potrzeby uzyskiwania dostępu do usług za pomocą klienta WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: dd767443fefb16ebc02300bffa4264357f12c3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280588"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="27b6a-103">Instrukcje: używanie elementu ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="27b6a-103">How to: Use the ChannelFactory</span></span>

<span data-ttu-id="27b6a-104">Klasa generyczna <xref:System.ServiceModel.ChannelFactory%601> jest używana w zaawansowanych scenariuszach, które wymagają utworzenia fabryki kanałów, której można użyć do utworzenia więcej niż jednego kanału.</span><span class="sxs-lookup"><span data-stu-id="27b6a-104">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="27b6a-105">Aby utworzyć i użyć klasy ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="27b6a-105">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="27b6a-106">Kompiluj i uruchamiaj usługę Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="27b6a-106">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="27b6a-107">Aby uzyskać więcej informacji, zobacz [projektowanie i implementowanie usług](../designing-and-implementing-services.md), [Konfigurowanie usług](../configuring-services.md)i [usług hostingowych](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="27b6a-107">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="27b6a-108">Użyj [Narzędzia do przesyłania metadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) do wygenerowania kontraktu (interfejsu) dla klienta.</span><span class="sxs-lookup"><span data-stu-id="27b6a-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="27b6a-109">W kodzie klienta Użyj <xref:System.ServiceModel.ChannelFactory%601> klasy, aby utworzyć odbiorniki wielu punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="27b6a-109">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27b6a-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="27b6a-110">Example</span></span>  

 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
