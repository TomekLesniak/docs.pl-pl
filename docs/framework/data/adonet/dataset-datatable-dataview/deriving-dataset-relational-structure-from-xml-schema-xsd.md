---
title: Pobieranie relacyjnej struktury elementu DataSet ze schematu XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 878e39af575328fb0abba096c327d36203a52231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164808"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="68174-102">Pobieranie relacyjnej struktury elementu DataSet ze schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="68174-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>

<span data-ttu-id="68174-103">Ta sekcja zawiera omówienie sposobu kompilowania schematu relacyjnego z `DataSet` dokumentu schematu języka definicji schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="68174-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="68174-104">Ogólnie rzecz biorąc dla każdego `complexType` elementu podrzędnego elementu schematu tabela jest generowana w `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="68174-105">Struktura tabeli jest określana na podstawie definicji typu złożonego.</span><span class="sxs-lookup"><span data-stu-id="68174-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="68174-106">Tabele są tworzone w programie `DataSet` dla elementów najwyższego poziomu w schemacie.</span><span class="sxs-lookup"><span data-stu-id="68174-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="68174-107">Jednak tabela jest tworzona tylko dla elementu najwyższego poziomu `complexType` `complexType` , gdy element jest zagnieżdżony wewnątrz innego `complexType` elementu, w którym to przypadku zagnieżdżony `complexType` element jest mapowany do `DataTable` wewnątrz `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="68174-108">Aby uzyskać więcej informacji na temat pliku XSD, zobacz temat schemat XML organizacja World Wide Web Consortium (W3C), [część 0: zalecenie podstawowe](https://www.w3.org/TR/xmlschema-0/), [część schematu XML 1: rekomendacja struktur](https://www.w3.org/TR/xmlschema-1/)i [schemat XML schematu część 2: rekomendacja typów](https://www.w3.org/TR/xmlschema-2/)danych.</span><span class="sxs-lookup"><span data-stu-id="68174-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="68174-109">Poniższy przykład ilustruje schemat XML `customers` , gdzie jest elementem podrzędnym `MyDataSet` elementu, który jest elementem **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="68174-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="68174-110">W poprzednim przykładzie element `customers` jest elementem typu złożonego.</span><span class="sxs-lookup"><span data-stu-id="68174-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="68174-111">W związku z tym definicja typu złożonego jest analizowana, a proces mapowania tworzy poniższą tabelę.</span><span class="sxs-lookup"><span data-stu-id="68174-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="68174-112">Typ danych każdej kolumny w tabeli pochodzi od typu schematu XML określonego elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="68174-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68174-113">Jeśli element `customers` składa się z prostego typu danych schematu XML, takiego jak **Integer**, nie jest generowana żadna tabela.</span><span class="sxs-lookup"><span data-stu-id="68174-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="68174-114">Tabele są tworzone tylko dla elementów najwyższego poziomu, które są typami złożonymi.</span><span class="sxs-lookup"><span data-stu-id="68174-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="68174-115">W poniższym schemacie XML element **schematu** ma dwa elementy podrzędne elementów `InStateCustomers` i `OutOfStateCustomers` .</span><span class="sxs-lookup"><span data-stu-id="68174-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="68174-116">`InStateCustomers` `OutOfStateCustomers` Elementy podrzędne i są elementami typu złożonego ( `customerType` ).</span><span class="sxs-lookup"><span data-stu-id="68174-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="68174-117">W związku z tym proces mapowania generuje następujące dwie identyczne tabele w `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="68174-118">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="68174-118">In This Section</span></span>  

 [<span data-ttu-id="68174-119">Mapowanie ograniczeń schematu XML (XSD) na ograniczenia elementu DataSet</span><span class="sxs-lookup"><span data-stu-id="68174-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="68174-120">Opisuje elementy schematu XML używane do tworzenia ograniczeń unique i FOREIGN KEY w `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="68174-121">Generowanie relacji elementu DataSet na podstawie schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="68174-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="68174-122">Opisuje elementy schematu XML używane do tworzenia relacji między kolumnami tabeli w `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="68174-123">Relacje i ograniczenia schematu XML</span><span class="sxs-lookup"><span data-stu-id="68174-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="68174-124">Opisuje, w jaki sposób relacje są tworzone niejawnie podczas używania elementów schematu XML do tworzenia ograniczeń w `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="68174-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68174-125">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="68174-125">Related Sections</span></span>  

 [<span data-ttu-id="68174-126">Używanie języka XML w elemencie DataSet</span><span class="sxs-lookup"><span data-stu-id="68174-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="68174-127">Opisuje sposób ładowania i utrwalania relacyjnej struktury i danych w `DataSet` postaci danych XML.</span><span class="sxs-lookup"><span data-stu-id="68174-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68174-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="68174-128">See also</span></span>

- [<span data-ttu-id="68174-129">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="68174-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
