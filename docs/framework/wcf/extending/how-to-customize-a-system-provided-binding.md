---
title: 'Instrukcje: dostosowywanie wiązania udostępnionego przez system'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: e3d7cb72bcbdd636530e7861071b73f8a5f38b31
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249231"
---
# <a name="how-to-customize-a-system-provided-binding"></a>Instrukcje: dostosowywanie wiązania udostępnionego przez system

Windows Communication Foundation (WCF) zawiera kilka powiązań dostarczonych przez system, które umożliwiają skonfigurowanie niektórych właściwości źródłowych elementów powiązania, ale nie wszystkich właściwości. W tym temacie pokazano, jak ustawić właściwości elementów powiązania w celu utworzenia niestandardowego powiązania.  
  
 Aby uzyskać więcej informacji na temat bezpośredniego tworzenia i konfigurowania elementów powiązania bez użycia powiązań dostarczonych przez system, zobacz [powiązania niestandardowe](custom-bindings.md).  
  
 Aby uzyskać więcej informacji na temat tworzenia i rozszerzania powiązań niestandardowych, zobacz [Rozszerzanie powiązań](extending-bindings.md).  
  
 W programie WCF wszystkie powiązania składają się z *elementów powiązania*. Każdy element powiązania pochodzi od <xref:System.ServiceModel.Channels.BindingElement> klasy. Powiązania dostarczone przez system, takie jak <xref:System.ServiceModel.BasicHttpBinding> Tworzenie i konfigurowanie własnych elementów powiązania. W tym temacie pokazano, jak uzyskać dostęp i zmienić właściwości tych elementów powiązania, które nie są bezpośrednio uwidocznione w powiązaniu; w specjalnej <xref:System.ServiceModel.BasicHttpBinding> klasie.  
  
 Poszczególne elementy powiązania są zawarte w kolekcji reprezentowanej przez <xref:System.ServiceModel.Channels.BindingElementCollection> klasę i są dodawane w następującej kolejności: przepływ transakcji, niezawodne sesje, zabezpieczenia, złożone dupleks, jednokierunkowe, zabezpieczenia strumieniowe, kodowanie komunikatów i transport. Należy zauważyć, że nie wszystkie elementy powiązania wymienione w każdym powiązaniu są wymagane. Elementy powiązań zdefiniowane przez użytkownika mogą być również wyświetlane w tej kolekcji elementów powiązania i muszą występować w takiej samej kolejności jak wcześniej. Na przykład transport zdefiniowany przez użytkownika musi być ostatnim elementem kolekcji elementów powiązania.  
  
 <xref:System.ServiceModel.BasicHttpBinding>Klasa zawiera trzy elementy powiązania:  
  
1. Opcjonalny element powiązania zabezpieczeń, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> Klasa używana z transportem http (zabezpieczenia na poziomie komunikatów) lub <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> Klasa, która jest używana, gdy warstwa transportu zapewnia zabezpieczenia, w tym przypadku jest używany transport https.  
  
2. Wymagany element powiązania kodera komunikatu ( <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> lub) <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> .  
  
3. Wymagany element powiązania transportu, albo <xref:System.ServiceModel.Channels.HttpTransportBindingElement> lub <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> .  
  
 W tym przykładzie utworzysz wystąpienie powiązania, wygeneruj *niestandardowe powiązanie* z niego, Przeanalizuj elementy powiązania w niestandardowym powiązaniu i po znalezieniu elementu powiązania HTTP ustawimy jego `KeepAliveEnabled` Właściwość na `false` . `KeepAliveEnabled`Właściwość nie jest uwidaczniana bezpośrednio w `BasicHttpBinding` , dlatego należy utworzyć niestandardowe powiązanie, aby przejść do elementu Binding i ustawić tę właściwość.  
  
### <a name="to-modify-a-system-provided-binding"></a>Aby zmodyfikować powiązanie dostarczone przez system  
  
1. Utwórz wystąpienie <xref:System.ServiceModel.BasicHttpBinding> klasy i ustaw jego tryb zabezpieczeń na poziom komunikatów.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2. Utwórz powiązanie niestandardowe na podstawie powiązania i Utwórz <xref:System.ServiceModel.Channels.BindingElementCollection> klasę z jednego z właściwości niestandardowego powiązania.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3. Pętla przez <xref:System.ServiceModel.Channels.BindingElementCollection> klasę i po znalezieniu <xref:System.ServiceModel.Channels.HttpTransportBindingElement> klasy, ustaw jej <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> Właściwość na `false` .  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Powiązania niestandardowe](custom-bindings.md)
