---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 82704aa40b508f1b1e2237c9768a7b7599c5c87e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158594"
---
# \<wsdlImporter>

<span data-ttu-id="a6588-101">Określa wszystkich importerów WSDL, którzy importują metadane Web Services Description Language (WSDL) 1,1 przy użyciu załączników WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="a6588-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="a6588-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6588-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6588-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a6588-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a6588-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a6588-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6588-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a6588-105">Attributes</span></span>  
  
|<span data-ttu-id="a6588-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a6588-106">Attribute</span></span>|<span data-ttu-id="a6588-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a6588-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a6588-108">Typ tego elementu.</span><span class="sxs-lookup"><span data-stu-id="a6588-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6588-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a6588-109">Child Elements</span></span>  

 <span data-ttu-id="a6588-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="a6588-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6588-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a6588-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a6588-112">Element</span><span class="sxs-lookup"><span data-stu-id="a6588-112">Element</span></span>|<span data-ttu-id="a6588-113">Opis</span><span class="sxs-lookup"><span data-stu-id="a6588-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="a6588-114">Określa wszystkich importerów WSDL, którzy importują metadane Web Services Description Language (WSDL) 1,1 przy użyciu załączników WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="a6588-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6588-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a6588-115">Remarks</span></span>  

 <span data-ttu-id="a6588-116">Importer WSDL jest używany do importowania metadanych, a także konwertowania tych informacji na różne klasy, które reprezentują informacje o kontrakcie i punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="a6588-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="a6588-117">Umożliwia selektywne importowanie informacji o kontraktach i punktach końcowych oraz właściwości, które uwidaczniają błędy importu i akceptują informacje o typie odpowiednie dla procesu importu i konwersji.</span><span class="sxs-lookup"><span data-stu-id="a6588-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="a6588-118">Obsługuje ona również importowanie informacji o powiązaniach i właściwości, które zapewniają dostęp do dowolnych dokumentów zasad, dokumentów WSDL, rozszerzeń WSDL i dokumentów schematu XML.</span><span class="sxs-lookup"><span data-stu-id="a6588-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6588-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a6588-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="a6588-120">Konfiguracja klienta programu WCF</span><span class="sxs-lookup"><span data-stu-id="a6588-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="a6588-121">Klienci</span><span class="sxs-lookup"><span data-stu-id="a6588-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
