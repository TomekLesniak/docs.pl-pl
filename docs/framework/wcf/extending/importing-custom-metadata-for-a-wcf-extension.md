---
title: Importowanie niestandardowych metadanych dla rozszerzenia WCF
ms.date: 03/30/2017
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
ms.openlocfilehash: b231ff676ffc81666713987a24605b8ae98bb6d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254626"
---
# <a name="importing-custom-metadata-for-a-wcf-extension"></a>Importowanie niestandardowych metadanych dla rozszerzenia WCF

W programie Windows Communication Foundation (WCF) Importowanie metadanych jest procesem generowania abstrakcyjnej reprezentacji usługi lub jej części składowych z metadanych. Na przykład WCF może importować <xref:System.ServiceModel.Description.ServiceEndpoint> wystąpienia, <xref:System.ServiceModel.Channels.Binding> wystąpienia lub <xref:System.ServiceModel.Description.ContractDescription> wystąpienia z dokumentu WSDL dla usługi. Aby zaimportować metadane usługi w programie WCF, należy użyć implementacji <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> klasy abstrakcyjnej. Typy, które pochodzą z <xref:System.ServiceModel.Description.MetadataImporter> klasy implementują obsługę importowania formatów metadanych, które wykorzystują logikę importu WS-Policy w programie WCF.  
  
 Metadane niestandardowe składają się z elementów XML, których nie można zaimportować przez importerów metadanych dostarczonych przez system. Zwykle dotyczy to niestandardowych rozszerzeń WSDL i potwierdzeń zasad niestandardowych.  
  
 W tej sekcji opisano sposób importowania niestandardowych rozszerzeń WSDL i potwierdzeń zasad. Nie koncentruje się na samym procesie importowania. Aby uzyskać więcej informacji na temat używania typów eksportujących i importowanych metadanych niezależnie od tego, czy metadane są niestandardowe czy obsługiwane przez system, zobacz [Eksportowanie i Importowanie metadanych](../feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Omówienie  

 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>Typ to implementacja <xref:System.ServiceModel.Description.MetadataImporter> klasy abstrakcyjnej dołączonej do WCF. <xref:System.ServiceModel.Description.WsdlImporter>Typ importuje metadane WSDL z dołączonymi zasadami, które są powiązane z <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> obiektem. Potwierdzenia zasad i rozszerzenia WSDL, które nie są rozpoznawane przez importerów domyślnie, są przesyłane do wszelkich zarejestrowanych zasad niestandardowych i importerów WSDL do importowania. Zwykle importerzy są wdrażani w celu obsługi elementów powiązania zdefiniowanych przez użytkownika lub modyfikacji zaimportowanego kontraktu.  
  
 W tej sekcji opisano:  
  
1. Jak zaimplementować i korzystać z <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interfejsu, który udostępnia dane WSDL niestandardowym importerom przed generowaniem opisów i generowaniem kodu. Tego interfejsu można użyć do sprawdzenia lub modyfikacji typów opisu i kompilowania kodu za pomocą danego zestawu metadanych.  
  
2. Jak zaimplementować i korzystać z <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interfejsu, który udostępnia potwierdzenia zasad przed wygenerowaniem obiektów opisu. Tego interfejsu można użyć do sprawdzenia lub zmodyfikowania powiązania lub kontraktu na podstawie pobranych zasad.  
  
 Aby uzyskać więcej informacji na temat eksportowania niestandardowych zatwierdzeń WSDL i zasad, zobacz [Eksportowanie niestandardowych metadanych dla rozszerzenia WCF](exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="importing-custom-wsdl-extensions"></a>Importowanie niestandardowych rozszerzeń WSDL  

 Aby dodać obsługę importowania rozszerzeń WSDL, zaimplementuj <xref:System.ServiceModel.Description.IWsdlImportExtension> interfejs, a następnie Dodaj implementację do <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> właściwości. <xref:System.ServiceModel.Description.WsdlImporter>Może również ładować implementacje <xref:System.ServiceModel.Description.IWsdlImportExtension> interfejsu zarejestrowanego w pliku konfiguracyjnym aplikacji. Należy zauważyć, że liczba importerów WSDL jest domyślnie rejestrowana, a kolejność zarejestrowanych importerów WSDL jest istotna.  
  
 Gdy niestandardowy importer WSDL jest ładowany i używany przez <xref:System.ServiceModel.Description.WsdlImporter> , najpierw <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A> wywoływana jest metoda, która umożliwia modyfikację metadanych przed procesem importu. Następnie umowy są importowane po <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A> wywołaniu metody, aby umożliwić modyfikację kontraktów zaimportowanych z metadanych. Na koniec <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A> Metoda jest wywoływana w celu włączenia modyfikacji importowanych punktów końcowych.  
  
 Aby uzyskać więcej informacji, zobacz [How to: import Custom WSDL](how-to-import-custom-wsdl.md).  
  
### <a name="importing-custom-policy-assertions"></a>Importowanie potwierdzeń zasad niestandardowych  

 <xref:System.ServiceModel.Description.WsdlImporter>Typ i [Narzędzie narzędzia metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) automatycznie obsługują przetwarzanie różnych typów potwierdzeń zasad w wyrażeniach zasad dołączonych do dokumentów WSDL. Te narzędzia zbierają, normalizuje i scalają wyrażenia zasad dołączone do powiązań WSDL i portów WSDL.  
  
 Aby dodać obsługę importowania potwierdzeń zasad niestandardowych, zaimplementuj <xref:System.ServiceModel.Description.IPolicyImportExtension> interfejs, a następnie Dodaj implementację do <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> właściwości. <xref:System.ServiceModel.Description.MetadataImporter>Może również ładować implementacje <xref:System.ServiceModel.Description.IPolicyImportExtension> interfejsu zarejestrowanego w pliku konfiguracyjnym aplikacji. Należy zauważyć, że liczba importerów zasad jest domyślnie rejestrowana i kolejność zarejestrowanego importera zasad jest istotna.  
  
 System metadanych wielokrotnie wywołuje <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> metodę we wszystkich zarejestrowanej rozszerzeniu importowania zasad dla każdej kombinacji alternatyw zasad dołączonych do tematów dotyczących wiadomości, operacji i zasad punktu końcowego. Podczas importowania portu WSDL zasady dołączone do portu i odpowiedniego powiązania WSDL są scalane przed wywołaniem ich w rozszerzeniach importu zasad. Alternatywy zasad są udostępniane za pomocą <xref:System.ServiceModel.Description.PolicyConversionContext> obiektów AS <xref:System.ServiceModel.Description.PolicyAssertionCollection> . Każda <xref:System.ServiceModel.Description.PolicyAssertionCollection> z nich jest kolekcją potwierdzeń zasad reprezentowanych przez <xref:System.Xml.XmlElement> obiekty.  
  
 <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A>Właściwości i <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A> <xref:System.ServiceModel.Description.PolicyConversionContext> obiektu uwidaczniają <xref:System.ServiceModel.Description.ContractDescription> <xref:System.ServiceModel.Channels.BindingElement> obiekty i, które zostały zaimportowane z WSDL. Rozszerzenia importowania zasad zatwierdzeń zasad, wyszukując wystąpienia określonego typu potwierdzenia zasad, wprowadzając odpowiednie zmiany w <xref:System.ServiceModel.Description.ContractDescription> <xref:System.ServiceModel.Channels.BindingElement> obiektach lub, a następnie usuwając potwierdzenia zasad z odpowiedniego <xref:System.ServiceModel.Description.PolicyAssertionCollection> wystąpienia.  
  
 `wsp:Optional`Atrybut i zagnieżdżone wyrażenia zasad nie są znormalizowane, dlatego rozszerzenia importu zasad muszą obsługiwać te konstrukcje zasad. Ponadto rozszerzenia importowania zasad mogą być wywoływane wiele razy z tymi samymi <xref:System.ServiceModel.Description.ContractDescription> i <xref:System.ServiceModel.Channels.BindingElement> obiektami, dlatego rozszerzenia importu zasad powinny być niezawodne dla tego zachowania.  
  
> [!IMPORTANT]
> Do importera mogą być przesyłane nieprawidłowe lub nieprawidłowe metadane. Upewnij się, że importerzy niestandardowi są niezawodne dla wszystkich form XML.  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: importowanie niestandardowych plików WSDL](how-to-import-custom-wsdl.md)
- [Instrukcje: importowanie niestandardowych asercji zasad](how-to-import-custom-policy-assertions.md)
- [Instrukcje: pisanie rozszerzenia dla typu ServiceContractGenerator](how-to-write-an-extension-for-the-servicecontractgenerator.md)
