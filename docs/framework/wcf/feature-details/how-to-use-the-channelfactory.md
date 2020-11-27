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
# <a name="how-to-use-the-channelfactory"></a>Instrukcje: używanie elementu ChannelFactory

Klasa generyczna <xref:System.ServiceModel.ChannelFactory%601> jest używana w zaawansowanych scenariuszach, które wymagają utworzenia fabryki kanałów, której można użyć do utworzenia więcej niż jednego kanału.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Aby utworzyć i użyć klasy ChannelFactory  
  
1. Kompiluj i uruchamiaj usługę Windows Communication Foundation (WCF). Aby uzyskać więcej informacji, zobacz [projektowanie i implementowanie usług](../designing-and-implementing-services.md), [Konfigurowanie usług](../configuring-services.md)i [usług hostingowych](../hosting-services.md).  
  
2. Użyj [Narzędzia do przesyłania metadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) do wygenerowania kontraktu (interfejsu) dla klienta.  
  
3. W kodzie klienta Użyj <xref:System.ServiceModel.ChannelFactory%601> klasy, aby utworzyć odbiorniki wielu punktów końcowych.  
  
## <a name="example"></a>Przykład  

 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
