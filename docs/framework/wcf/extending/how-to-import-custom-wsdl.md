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
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="e999e-102">Instrukcje: importowanie niestandardowych plików WSDL</span><span class="sxs-lookup"><span data-stu-id="e999e-102">How to: Import Custom WSDL</span></span>

<span data-ttu-id="e999e-103">W tym temacie opisano sposób importowania niestandardowego WSDL.</span><span class="sxs-lookup"><span data-stu-id="e999e-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="e999e-104">Aby obsłużyć niestandardowy WSDL, należy zaimplementować <xref:System.ServiceModel.Description.IWsdlImportExtension> interfejs.</span><span class="sxs-lookup"><span data-stu-id="e999e-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="e999e-105">Aby zaimportować niestandardowy element WSDL</span><span class="sxs-lookup"><span data-stu-id="e999e-105">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="e999e-106">Implementacja <xref:System.ServiceModel.Description.IWsdlImportExtension> .</span><span class="sxs-lookup"><span data-stu-id="e999e-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="e999e-107">Zaimplementuj <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> metodę, aby zmodyfikować metadane przed zaimportowaniem.</span><span class="sxs-lookup"><span data-stu-id="e999e-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="e999e-108">Zaimplementuj <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> metody i, <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> Aby zmodyfikować kontrakty i punkty końcowe zaimportowane z metadanych.</span><span class="sxs-lookup"><span data-stu-id="e999e-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="e999e-109">Aby uzyskać dostęp do zaimportowanego kontraktu lub punktu końcowego, użyj odpowiedniego obiektu kontekstu ( <xref:System.ServiceModel.Description.WsdlContractConversionContext> lub <xref:System.ServiceModel.Description.WsdlEndpointConversionContext> ):</span><span class="sxs-lookup"><span data-stu-id="e999e-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
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
  
2. <span data-ttu-id="e999e-110">Skonfiguruj aplikację kliencką tak, aby korzystała z niestandardowego importera WSDL.</span><span class="sxs-lookup"><span data-stu-id="e999e-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="e999e-111">Należy pamiętać, że w przypadku korzystania z Svcutil.exe należy dodać tę konfigurację do pliku konfiguracji dla Svcutil.exe (Svcutil.exe.config):</span><span class="sxs-lookup"><span data-stu-id="e999e-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
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
  
3. <span data-ttu-id="e999e-112">Utwórz nowe <xref:System.ServiceModel.Description.WsdlImporter> wystąpienie (przekazanie <xref:System.ServiceModel.Description.MetadataSet> wystąpienia zawierającego dokumenty WSDL, które chcesz zaimportować) i Wywołaj <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> :</span><span class="sxs-lookup"><span data-stu-id="e999e-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e999e-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e999e-113">See also</span></span>

- [<span data-ttu-id="e999e-114">Metadane</span><span class="sxs-lookup"><span data-stu-id="e999e-114">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="e999e-115">Eksportowanie i importowanie metadanych</span><span class="sxs-lookup"><span data-stu-id="e999e-115">Exporting and Importing Metadata</span></span>](../feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="e999e-116">Niestandardowa publikacja WSDL</span><span class="sxs-lookup"><span data-stu-id="e999e-116">Custom WSDL Publication</span></span>](../samples/custom-wsdl-publication.md)
