---
title: Generowanie biblioteki klienta usługi danych (Usługi danych programu WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 050a791736e90b5daf46fd272197ca21a220afb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172622"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="28223-102">Generowanie biblioteki klienta usługi danych (Usługi danych programu WCF)</span><span class="sxs-lookup"><span data-stu-id="28223-102">Generating the Data Service Client Library (WCF Data Services)</span></span>

<span data-ttu-id="28223-103">Usługa danych, która implementuje protokół Open Data Protocol (OData), może zwrócić dokument metadanych usługi, który opisuje model danych uwidoczniony przez kanał informacyjny OData.</span><span class="sxs-lookup"><span data-stu-id="28223-103">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="28223-104">Aby uzyskać więcej informacji, zobacz sekcję dotyczącą dokumentu metadanych usługi w artykule dotyczącym protokołu [OData: przegląd](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="28223-104">For more information, see the Service Metadata Document section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span> <span data-ttu-id="28223-105">Możesz użyć okna dialogowego **Dodaj odwołanie do usługi** w programie Visual Studio, aby dodać odwołanie do usługi opartej na protokole OData.</span><span class="sxs-lookup"><span data-stu-id="28223-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="28223-106">W przypadku użycia tego narzędzia do dodania odwołania do metadanych zwracanych przez źródło danych OData w projekcie klienta wykonywane są następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="28223-106">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="28223-107">Żąda dokumentu metadanych usługi z usługi danych i interpretuje zwrócone metadane.</span><span class="sxs-lookup"><span data-stu-id="28223-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="28223-108">Zwrócone metadane są przechowywane w projekcie klienta jako plik. edmx.</span><span class="sxs-lookup"><span data-stu-id="28223-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="28223-109">Nie można otworzyć tego pliku edmx przy użyciu projektanta Entity Data Model, ponieważ nie ma on tego samego formatu pliku. edmx, który jest używany przez Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="28223-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="28223-110">Ten plik metadanych można wyświetlić za pomocą edytora XML lub dowolnego edytora tekstu.</span><span class="sxs-lookup"><span data-stu-id="28223-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="28223-111">Aby uzyskać więcej informacji, zobacz [ \[ MC-EDMX \] : Entity Data Model dla Data Services format pakietu](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span><span class="sxs-lookup"><span data-stu-id="28223-111">For more information, see [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span></span>
  
- <span data-ttu-id="28223-112">Generuje reprezentację usługi jako klasę kontenera jednostek, która dziedziczy z <xref:System.Data.Services.Client.DataServiceContext> .</span><span class="sxs-lookup"><span data-stu-id="28223-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="28223-113">Ta klasa kontenerów jednostek jest podobna do kontenera jednostek wygenerowanego przez narzędzia Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="28223-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="28223-114">Aby uzyskać więcej informacji, zobacz temat [usługi obiektów — omówienie (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="28223-114">For more information, see [Object Services Overview (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="28223-115">Generuje klasy danych dla typów modeli danych odnajdywanych w metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="28223-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="28223-116">Dodaje odwołanie do `System.Data.Services.Client` zestawu do projektu.</span><span class="sxs-lookup"><span data-stu-id="28223-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="28223-117">Aby uzyskać więcej informacji, zobacz [jak: Dodawanie odwołania do usługi danych](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28223-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="28223-118">Klasy usługi danych klienta można również wygenerować przy użyciu narzędzia [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="28223-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="28223-119">Aby uzyskać więcej informacji, zobacz [jak: ręczne generowanie klas usługi danych klienta](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28223-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="28223-120">Mapowanie typu danych klienta</span><span class="sxs-lookup"><span data-stu-id="28223-120">Client Data Type Mapping</span></span>  

 <span data-ttu-id="28223-121">W przypadku korzystania z okna dialogowego **Dodaj odwołanie do usługi** w programie Visual Studio lub `DataSvcUtil.exe` Narzędzia do generowania klas danych klienta, które są oparte na strumieniowym źródle danych OData, typy danych .NET Framework są mapowane na typy pierwotne z modelu dane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="28223-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="28223-122">Typ modelu danych</span><span class="sxs-lookup"><span data-stu-id="28223-122">Data model type</span></span>|<span data-ttu-id="28223-123">Typ danych .NET Framework</span><span class="sxs-lookup"><span data-stu-id="28223-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="28223-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="28223-124"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="28223-125">Aby uzyskać więcej informacji, zobacz sekcję typy danych pierwotnych w artykule dotyczącym usługi [OData: przegląd](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="28223-125">For more information, see the Primitive Data Types section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28223-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="28223-126">See also</span></span>

- [<span data-ttu-id="28223-127">Biblioteka klienta usług danych WCF</span><span class="sxs-lookup"><span data-stu-id="28223-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="28223-128">Szybki start</span><span class="sxs-lookup"><span data-stu-id="28223-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
