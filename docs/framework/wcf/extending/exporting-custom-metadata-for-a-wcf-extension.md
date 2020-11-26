---
title: Eksportowanie niestandardowych metadanych na potrzeby rozszerzenia programu WCF
ms.date: 03/30/2017
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
ms.openlocfilehash: 1aad43eb59a92df9376577ba0108661a0cb9cd87
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249335"
---
# <a name="exporting-custom-metadata-for-a-wcf-extension"></a>Eksportowanie niestandardowych metadanych na potrzeby rozszerzenia programu WCF

W programie Windows Communication Foundation (WCF) Eksport metadanych to proces opisywania punktów końcowych usługi i projekcji ich w równoległej, ustandaryzowanej reprezentacji, z której klienci mogą zrozumieć, jak korzystać z usługi. Metadane niestandardowe składają się z elementów XML, których nie można eksportować przez eksporterów metadanych dostarczonych przez system. Zazwyczaj obejmuje to niestandardowe elementy WSDL dla zachowań zdefiniowanych przez użytkownika i elementów powiązania oraz potwierdzeń zasad o możliwościach i wymaganiach dotyczących powiązań i umów.  
  
 W tej sekcji opisano eksportowanie niestandardowych zatwierdzeń WSDL lub zasad i nie koncentruje się na samym procesie eksportowania. Aby uzyskać więcej informacji na temat korzystania z typów eksportujących i importowanych metadanych niezależnie od tego, czy metadane są niestandardowe, czy skonstruowane przez system, zobacz [Eksportowanie i Importowanie metadanych](../feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Omówienie  

 Gdy metadane są publikowane przy użyciu <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> , <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> są badane i XSD oraz WSDL — łącznie z potwierdzeniami zasad — są generowane dla wszystkich kontraktów i powiązań, które mogą być obsługiwane przez funkcję WCF przy użyciu atrybutów i powiązań dostarczonych przez system. Jednak atrybuty zachowań niestandardowych lub elementy powiązania wymagają obsługi, zanim będą mogły zostać prawidłowo wyeksportowane.  
  
 W tej sekcji opisano:  
  
1. Jak zaimplementować i korzystać z <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interfejsu, który udostępnia dane generacji WSDL przed opublikowaniem WSDL.  
  
2. Jak zaimplementować i korzystać z <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interfejsu, który udostępnia dane zasad przed wyeksportowaniem potwierdzeń zasad w danych WSDL.  
  
 Aby uzyskać więcej informacji na temat importowania niestandardowych zatwierdzeń WSDL i zasad, zobacz [Importowanie niestandardowych metadanych dla rozszerzenia WCF](importing-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-custom-wsdl-elements"></a>Eksportowanie niestandardowych elementów WSDL  

 Zaimplementuj <xref:System.ServiceModel.Description.IWsdlExportExtension> operacje na działaniach, zachowanie kontraktowe, zachowanie punktu końcowego lub element powiązania ( <xref:System.ServiceModel.Description.IOperationBehavior> , <xref:System.ServiceModel.Description.IContractBehavior> , <xref:System.ServiceModel.Description.IEndpointBehavior> lub <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> odpowiednio) i Wstaw elementy zachowań lub powiązania do opisu usługi, którą chcesz wyeksportować. (Aby uzyskać więcej informacji na temat wstawiania zachowań, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md)). <xref:System.ServiceModel.Description.IWsdlExportExtension>Jest wywoływana dla każdego punktu końcowego, a każdy punkt końcowy eksportuje kontrakt jako pierwszy, jeśli nie został jeszcze wyeksportowany. W zależności od potrzeb można wziąć udział w procesie eksportu:  
  
- Użyj, <xref:System.ServiceModel.Description.WsdlContractConversionContext> Aby zmodyfikować wyeksportowane metadane w <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> metodzie.  
  
- Użyj, <xref:System.ServiceModel.Description.WsdlEndpointConversionContext> Aby zmodyfikować eksportowane metadane dla punktu końcowego w <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> metodzie.  
  
 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>Metoda jest wywoływana dla wszystkich <xref:System.ServiceModel.Description.IWsdlExportExtension> implementacji w <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> wyeksportowanym wystąpieniu.  <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A>Metoda jest wywoływana dla wszystkich <xref:System.ServiceModel.Description.IWsdlExportExtension> implementacji z <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> wyeksportowanym wystąpieniem.  
  
 Aby uzyskać więcej informacji, zobacz [jak: eksportowanie NIESTANDARDOWEGO WSDL](how-to-export-custom-wsdl.md) i przykład [niestandardowej publikacji WSDL](../samples/custom-wsdl-publication.md).  
  
## <a name="exporting-custom-policy-assertions"></a>Eksportowanie zatwierdzeń zasad niestandardowych  

 Zaimplementuj <xref:System.ServiceModel.Description.IPolicyExportExtension> obiekt na <xref:System.ServiceModel.Channels.BindingElement> a i Dodaj element Binding do powiązania, aby zapisać niestandardowe potwierdzenia zasad dotyczące obsługi powiązań i możliwości kontraktu w języku WSDL. <xref:System.ServiceModel.Description.IPolicyExportExtension>Jest wywoływana raz podczas eksportowania zaimplementowanego elementu Binding w powiązaniu i przekazuje <xref:System.ServiceModel.Description.PolicyConversionContext> do <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> metody. Można użyć metod w <xref:System.ServiceModel.Description.PolicyConversionContext> wystąpieniu, aby dodać do potwierdzeń zasad dołączonych do powiązania WSDL w tematach komunikatów, operacji lub punktów końcowych.  
  
 Aby uzyskać więcej informacji, zobacz [jak: eksportowanie niestandardowych zatwierdzeń zasad](how-to-export-custom-policy-assertions.md).  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: eksportowanie niestandardowych informacji w formacie WSDL](how-to-export-custom-wsdl.md)
- [Instrukcje: eksportowanie niestandardowych asercji zasad](how-to-export-custom-policy-assertions.md)
- [Importowanie niestandardowych metadanych dla rozszerzenia WCF](importing-custom-metadata-for-a-wcf-extension.md)
