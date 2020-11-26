---
title: 'Instrukcje: eksportowanie niestandardowych asercji zasad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
ms.openlocfilehash: 8bdc9948d6846631fde1d428c113682f40d15ec3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249218"
---
# <a name="how-to-export-custom-policy-assertions"></a>Instrukcje: eksportowanie niestandardowych asercji zasad

Potwierdzenia zasad opisują możliwości i wymagania punktu końcowego usługi. Aplikacje usług mogą używać niestandardowych potwierdzeń zasad w metadanych usługi do przekazywania informacji o dostosowywaniu punktów końcowych, powiązań lub umów do aplikacji klienckiej. Za pomocą Windows Communication Foundation (WCF) można eksportować potwierdzenia w wyrażeniach zasad dołączonych do powiązań WSDL w podmiotach punktu końcowego, operacji lub komunikatu, w zależności od możliwości lub wymagań, które komunikujesz.  
  
 Potwierdzenia zasad niestandardowych są eksportowane przez zaimplementowanie <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interfejsu na <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> i wstawianie elementu powiązania bezpośrednio do powiązania punktu końcowego usługi lub przez zarejestrowanie elementu powiązania w pliku konfiguracyjnym aplikacji. Implementacja eksportu zasad powinna dodać potwierdzenie zasad niestandardowych jako <xref:System.Xml.XmlElement?displayProperty=nameWithType> wystąpienie do odpowiedniej <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> metody w przekazaniu na <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> metodę.  
  
 Ponadto należy sprawdzić <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> Właściwość <xref:System.ServiceModel.Description.WsdlExporter> klasy i wyeksportować zagnieżdżone wyrażenia zasad i atrybuty struktury zasad w prawidłowej przestrzeni nazw na podstawie określonej wersji zasad.  
  
 Aby zaimportować potwierdzenia zasad niestandardowych, zobacz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> i [instrukcje: Importowanie potwierdzeń zasad niestandardowych](how-to-import-custom-policy-assertions.md).  
  
### <a name="to-export-custom-policy-assertions"></a>Aby wyeksportować potwierdzenia zasad niestandardowych  
  
1. Zaimplementuj <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interfejs na <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> . Poniższy przykład kodu pokazuje implementację niestandardowej potwierdzeń zasad na poziomie powiązania.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2. Wstaw element Binding do powiązania punktu końcowego albo programowo lub za pomocą pliku konfiguracji aplikacji. Zapoznaj się z poniższymi procedurami.  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a>Aby wstawić element powiązania przy użyciu pliku konfiguracji aplikacji  
  
1. Zaimplementuj <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> dla elementu niestandardowego powiązania potwierdzenia zasad.  
  
2. Dodaj rozszerzenie elementu Binding do pliku konfiguracji przy użyciu [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) elementu.  
  
3. Utwórz niestandardowe powiązanie przy użyciu <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> .  
  
### <a name="to-insert-a-binding-element-programmatically"></a>Aby programowo wstawić element powiązania  
  
1. Utwórz nowy <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> i dodaj go do <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> .  
  
2. Dodaj niestandardowe powiązanie z kroku 1. do nowego punktu końcowego i Dodaj nowy punkt końcowy usługi do elementu, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> wywołując <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> metodę.  
  
3. Otwórz klasę <xref:System.ServiceModel.ServiceHost>. Poniższy przykład kodu pokazuje Tworzenie niestandardowego powiązania i programistyczne Wstawianie elementów powiązania.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.IPolicyImportExtension>
- <xref:System.ServiceModel.Description.IPolicyExportExtension>
- [Instrukcje: importowanie niestandardowych asercji zasad](how-to-import-custom-policy-assertions.md)
