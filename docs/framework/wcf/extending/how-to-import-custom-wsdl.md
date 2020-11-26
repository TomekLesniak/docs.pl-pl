---
title: 'Instrukcje: importowanie niestandardowych plików WSDL'
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: c5aa554394743314a91afd6a5cdf86f9974e81f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249088"
---
# <a name="how-to-import-custom-wsdl"></a>Instrukcje: importowanie niestandardowych plików WSDL

W tym temacie opisano sposób importowania niestandardowego WSDL. Aby obsłużyć niestandardowy WSDL, należy zaimplementować <xref:System.ServiceModel.Description.IWsdlImportExtension> interfejs.  
  
### <a name="to-import-custom-wsdl"></a>Aby zaimportować niestandardowy element WSDL  
  
1. Implementacja <xref:System.ServiceModel.Description.IWsdlImportExtension> . Zaimplementuj <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> metodę, aby zmodyfikować metadane przed zaimportowaniem. Zaimplementuj <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> metody i, <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> Aby zmodyfikować kontrakty i punkty końcowe zaimportowane z metadanych. Aby uzyskać dostęp do zaimportowanego kontraktu lub punktu końcowego, użyj odpowiedniego obiektu kontekstu ( <xref:System.ServiceModel.Description.WsdlContractConversionContext> lub <xref:System.ServiceModel.Description.WsdlEndpointConversionContext> ):  
  
    ```csharp
    public class WsdlDocumentationImporter : IWsdlImportExtension
    {
        public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)
        {
            // Contract documentation
            if (context.WsdlPortType.Documentation != null)
            {
                context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));
            }
            // Operation documentation
            foreach (Operation operation in context.WsdlPortType.Operations)
            {
                if (operation.Documentation != null)
                {
                    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);
                    if (operationDescription != null)
                    {
                        operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));
                    }
                }
            }
        }

        public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)
        {
            Console.WriteLine("BeforeImport called.");
        }

        public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)
        {
            Console.WriteLine("ImportEndpoint called.");
        }
    }
    ```
  
2. Skonfiguruj aplikację kliencką tak, aby korzystała z niestandardowego importera WSDL. Należy pamiętać, że w przypadku korzystania z Svcutil.exe należy dodać tę konfigurację do pliku konfiguracji dla Svcutil.exe (Svcutil.exe.config):  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint
              address="http://localhost:8000/Fibonacci"
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3. Utwórz nowe <xref:System.ServiceModel.Description.WsdlImporter> wystąpienie (przekazanie <xref:System.ServiceModel.Description.MetadataSet> wystąpienia zawierającego dokumenty WSDL, które chcesz zaimportować) i Wywołaj <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> :  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>Zobacz też

- [Metadane](../feature-details/metadata.md)
- [Eksportowanie i importowanie metadanych](../feature-details/exporting-and-importing-metadata.md)
- [Niestandardowa publikacja WSDL](../samples/custom-wsdl-publication.md)
