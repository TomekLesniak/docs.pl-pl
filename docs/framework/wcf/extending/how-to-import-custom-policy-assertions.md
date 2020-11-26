---
title: 'Instrukcje: importowanie niestandardowych asercji zasad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
ms.openlocfilehash: fb5e3ba5faca1b32eef63ac174bcd7731ee50771
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249153"
---
# <a name="how-to-import-custom-policy-assertions"></a>Instrukcje: importowanie niestandardowych asercji zasad

Potwierdzenia zasad opisują możliwości i wymagania punktu końcowego usługi.  Aplikacje klienckie mogą używać potwierdzeń zasad w metadanych usługi, aby skonfigurować powiązanie klienta lub dostosować kontrakt usługi dla punktu końcowego usługi.  
  
 Niestandardowe potwierdzenia zasad są importowane przez implementację <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interfejsu i przekazanie tego obiektu do systemu metadanych lub przez zarejestrowanie typu implementacji w pliku konfiguracyjnym aplikacji.  Implementacje <xref:System.ServiceModel.Description.IPolicyImportExtension> interfejsu muszą udostępniać Konstruktor bez parametrów.  
  
### <a name="to-import-custom-policy-assertions"></a>Aby zaimportować potwierdzenia zasad niestandardowych  
  
1. Zaimplementuj <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interfejs w klasie. Zapoznaj się z poniższymi procedurami.  
  
2. Wstaw importera zasad niestandardowych przez:  
  
3. Przy użyciu pliku konfiguracji. Zapoznaj się z poniższymi procedurami.  
  
4. Użycie pliku konfiguracji z [narzędziem do przesyłania metadanych programu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Zapoznaj się z poniższymi procedurami.  
  
5. Programowe Wstawianie importera zasad. Zapoznaj się z poniższymi procedurami.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>Aby zaimplementować interfejs System. ServiceModel. Description. IPolicyImportExtension dla dowolnej klasy  
  
1. W <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> przypadku poszczególnych interesujących Cię zasad Znajdź potwierdzenia zasad, które chcesz zaimportować, wywołując odpowiednią metodę (w zależności od żądanego zakresu potwierdzenia) w <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> obiekcie przekazanym do metody. Poniższy przykład kodu pokazuje, jak za pomocą <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> metody zlokalizować potwierdzenie zasad niestandardowych i usunąć je z kolekcji w jednym kroku. Jeśli używasz metody Remove do lokalizowania i usuwania potwierdzenia, nie musisz wykonywać kroku 4.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2. Przetwarzanie potwierdzeń zasad. Należy pamiętać, że system zasad nie normalizuje zasad zagnieżdżonych i `wsp:optional` . Należy przetwarzać te konstrukcje w implementacji rozszerzenia importu zasad.  
  
3. Wykonaj dostosowanie do powiązania lub kontraktu, który obsługuje możliwości lub wymagania określone przez potwierdzenie zasad. Zazwyczaj potwierdzenia wskazują, że powiązanie wymaga określonej konfiguracji lub określonego elementu powiązania. Wprowadź te modyfikacje, uzyskując dostęp do <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType> właściwości. Inne potwierdzenia wymagają zmodyfikowania kontraktu.  Możesz uzyskać dostęp do kontraktu i zmodyfikować go przy użyciu <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType> właściwości.  Należy zauważyć, że importer zasad może być wywoływany wiele razy dla tego samego powiązania i kontraktu, ale różne alternatywy dla zasad, jeśli Importowanie alternatywy zasad zakończy się niepowodzeniem. Kod powinien być odporny na to zachowanie.  
  
4. Usuń potwierdzenie zasad niestandardowych z kolekcji potwierdzenia. Jeśli nie usuniesz Windows Communication Foundation potwierdzenia (WCF), przyjęto założenie, że import zasad nie powiódł się i nie importuje skojarzonego powiązania. Jeśli użyto metody, <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> Aby zlokalizować potwierdzenie zasad niestandardowych i usunąć je z kolekcji w jednym kroku, nie musisz wykonywać tego kroku.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>Aby wstawić importera zasad niestandardowych do systemu metadanych przy użyciu pliku konfiguracji  
  
1. Dodaj typ importera do `<extensions>` elementu wewnątrz [\<policyImporters>](../../configure-apps/file-schema/wcf/policyimporters.md) elementu w pliku konfiguracji klienta.  
  
     [!code-xml[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]
  
2. W aplikacji klienckiej Użyj lub, <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> Aby rozwiązać metadane, a importer jest wywoływany automatycznie.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>Aby wstawić importera zasad niestandardowych do systemu metadanych przy użyciu Svcutil.exe  
  
1. Dodaj typ importera do `<extensions>` elementu wewnątrz [\<policyImporters>](../../configure-apps/file-schema/wcf/policyimporters.md) elementu w pliku konfiguracji Svcutil.exe.config. Możesz również wskazać Svcutil.exe, aby załadować typy importerów zasad zarejestrowane w innym pliku konfiguracji przy użyciu `/svcutilConfig` opcji.  
  
2. Użyj narzędzia do zaimportowania metadanych programu [ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , aby zaimportować metadane, a importer jest wywoływany automatycznie.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>Aby programowo wstawić importera zasad niestandardowych do systemu metadanych  
  
1. Dodaj importera do <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> właściwości (na przykład jeśli używasz <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> ) przed zaimportowaniem metadanych.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>
- [Rozszerzanie systemu metadanych](extending-the-metadata-system.md)
