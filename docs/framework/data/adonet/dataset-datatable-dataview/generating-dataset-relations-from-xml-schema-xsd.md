---
title: Generowanie relacji elementu DataSet na podstawie schematu XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 2673280ebb94dcc10c130f3969f3e3250d3706a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198590"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="94c84-102">Generowanie relacji elementu DataSet na podstawie schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="94c84-102">Generating DataSet Relations from XML Schema (XSD)</span></span>

<span data-ttu-id="94c84-103">W programie <xref:System.Data.DataSet> można utworzyć skojarzenie między dwiema lub więcej kolumnami przez utworzenie relacji nadrzędny-podrzędny.</span><span class="sxs-lookup"><span data-stu-id="94c84-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="94c84-104">Istnieją trzy sposoby reprezentowania relacji **zestawu danych** w schemacie języka definicji schematu XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="94c84-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="94c84-105">Określ zagnieżdżone typy złożone.</span><span class="sxs-lookup"><span data-stu-id="94c84-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="94c84-106">Użyj adnotacji **msdata: Relationship** .</span><span class="sxs-lookup"><span data-stu-id="94c84-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="94c84-107">Określ element **xs: keyref** bez adnotacji **msdata: ConstraintOnly** .</span><span class="sxs-lookup"><span data-stu-id="94c84-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="94c84-108">Zagnieżdżone typy złożone</span><span class="sxs-lookup"><span data-stu-id="94c84-108">Nested Complex Types</span></span>  

 <span data-ttu-id="94c84-109">Zagnieżdżone definicje typu złożonego w schemacie wskazują relacje nadrzędny-podrzędny elementów.</span><span class="sxs-lookup"><span data-stu-id="94c84-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="94c84-110">Poniższy fragment schematu XML pokazuje, że **OrderDetail** jest elementem podrzędnym elementu **Order** .</span><span class="sxs-lookup"><span data-stu-id="94c84-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="94c84-111">Proces mapowania schematu XML tworzy tabele w **zestawie danych** , które odnoszą się do zagnieżdżonych typów złożonych w schemacie.</span><span class="sxs-lookup"><span data-stu-id="94c84-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="94c84-112">Tworzy również dodatkowe kolumny, które są używane jako nadrzędne **-** kolumny podrzędne dla wygenerowanych tabel.</span><span class="sxs-lookup"><span data-stu-id="94c84-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="94c84-113">Należy zauważyć, że te nadrzędne **-** kolumny podrzędne określają relacje, które nie są takie same jak określanie ograniczeń klucza podstawowego/klucza obcego.</span><span class="sxs-lookup"><span data-stu-id="94c84-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="94c84-114">msdata: adnotacja relacji</span><span class="sxs-lookup"><span data-stu-id="94c84-114">msdata:Relationship Annotation</span></span>  

 <span data-ttu-id="94c84-115">Adnotacja **msdata: Relationship** pozwala jawnie określić relacje nadrzędny-podrzędny między elementami w schemacie, które nie są zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="94c84-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="94c84-116">Poniższy przykład pokazuje strukturę elementu **Relationship** .</span><span class="sxs-lookup"><span data-stu-id="94c84-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="94c84-117">Atrybuty **msdata:** adnotacja relacji identyfikują elementy należące do relacji nadrzędny-podrzędny, a także elementy **ParentKey** i **ChildKey** oraz atrybuty powiązane z relacją.</span><span class="sxs-lookup"><span data-stu-id="94c84-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="94c84-118">Proces mapowania używa tych informacji do generowania tabel w **zestawie danych** i tworzenia relacji klucz podstawowy/klucz obcy między tymi tabelami.</span><span class="sxs-lookup"><span data-stu-id="94c84-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="94c84-119">Na przykład poniższy fragment schematu określa **kolejność** i **OrderDetail** elementów na tym samym poziomie (niezagnieżdżony).</span><span class="sxs-lookup"><span data-stu-id="94c84-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="94c84-120">Schemat określa **msdata:** adnotację relacji, która określa relację nadrzędny-podrzędny między tymi dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="94c84-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="94c84-121">W takim przypadku należy określić jawną relację przy użyciu adnotacji **msdata: Relationship** .</span><span class="sxs-lookup"><span data-stu-id="94c84-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="94c84-122">Proces mapowania używa elementu **Relationship** , aby utworzyć relację nadrzędny-podrzędny między kolumną **OrderNumber** w tabeli **Order** i kolumną **OrderNo** w tabeli **OrderDetail** w **zestawie danych**.</span><span class="sxs-lookup"><span data-stu-id="94c84-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="94c84-123">Proces mapowania określa tylko relację; nie określa ona automatycznie żadnych ograniczeń dotyczących wartości w tych kolumnach, tak jak ograniczenia klucz podstawowy/klucz obcy w relacyjnych bazach danych.</span><span class="sxs-lookup"><span data-stu-id="94c84-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="94c84-124">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="94c84-124">In This Section</span></span>  

 [<span data-ttu-id="94c84-125">Mapowanie niejawnych relacji między zagnieżdżonymi elementami schematu</span><span class="sxs-lookup"><span data-stu-id="94c84-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="94c84-126">Opisuje ograniczenia i relacje, które są niejawnie tworzone w **zestawie danych** podczas napotkania zagnieżdżonych elementów w schemacie XML.</span><span class="sxs-lookup"><span data-stu-id="94c84-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="94c84-127">Mapowanie relacji określonych dla zagnieżdżonych elementów</span><span class="sxs-lookup"><span data-stu-id="94c84-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="94c84-128">Opisuje, jak jawnie ustawić relacje w **zestawie danych** dla zagnieżdżonych elementów w schemacie XML.</span><span class="sxs-lookup"><span data-stu-id="94c84-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="94c84-129">Określanie relacji między elementami bez zagnieżdżania</span><span class="sxs-lookup"><span data-stu-id="94c84-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="94c84-130">Opisuje sposób tworzenia relacji w **zestawie danych** między elementami schematu XML, które nie są zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="94c84-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="94c84-131">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="94c84-131">Related Sections</span></span>  

 [<span data-ttu-id="94c84-132">Pobieranie relacyjnej struktury elementu DataSet ze schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="94c84-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="94c84-133">Opisuje strukturę relacyjną lub schemat **zestawu danych** , który jest tworzony na podstawie schematu definicji schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="94c84-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="94c84-134">Mapowanie ograniczeń schematu XML (XSD) na ograniczenia elementu DataSet</span><span class="sxs-lookup"><span data-stu-id="94c84-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="94c84-135">Opisuje elementy schematu XML używane do tworzenia ograniczeń unikatowych i obcych kluczy w **zestawie danych**.</span><span class="sxs-lookup"><span data-stu-id="94c84-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c84-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="94c84-136">See also</span></span>

- [<span data-ttu-id="94c84-137">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94c84-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
