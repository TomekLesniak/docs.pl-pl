---
title: Mapowanie ograniczeń unique schematu XML (XSD) na ograniczenia elementu DataSet
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 3b2dad44176e52adcf32e2e3ccff3d82ba23f6ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153238"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="9e940-102">Mapowanie ograniczeń unique schematu XML (XSD) na ograniczenia elementu DataSet</span><span class="sxs-lookup"><span data-stu-id="9e940-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="9e940-103">W schemacie języka definicji schematu XML (XSD) **unikatowy** element określa ograniczenie unikatowości dla elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9e940-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="9e940-104">W procesie tłumaczenia schematu XML na schemat relacyjny, unikatowe ograniczenie określone dla elementu lub atrybutu w schemacie XML jest zamapowane na unikatowe ograniczenie w polu <xref:System.Data.DataTable> w odpowiedniej <xref:System.Data.DataSet> generacji.</span><span class="sxs-lookup"><span data-stu-id="9e940-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="9e940-105">Poniższa tabela zawiera opis atrybutów **msdata** , które można określić w **unikatowym** elemencie.</span><span class="sxs-lookup"><span data-stu-id="9e940-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="9e940-106">Nazwa atrybutu</span><span class="sxs-lookup"><span data-stu-id="9e940-106">Attribute name</span></span>|<span data-ttu-id="9e940-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9e940-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9e940-108">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="9e940-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="9e940-109">Jeśli ten atrybut jest określony, jego wartość jest używana jako nazwa ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="9e940-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="9e940-110">W przeciwnym razie atrybut **name** zawiera wartość nazwy ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="9e940-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="9e940-111">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="9e940-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="9e940-112">Jeśli `PrimaryKey="true"` jest obecny w elemencie **unikatowym** , zostanie utworzone unikatowe ograniczenie z właściwością **IsPrimaryKey** ustawioną na **wartość true**.</span><span class="sxs-lookup"><span data-stu-id="9e940-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="9e940-113">W poniższym przykładzie przedstawiono schemat XML, który używa **unikatowego** elementu do określenia ograniczenia unikatowości.</span><span class="sxs-lookup"><span data-stu-id="9e940-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="9e940-114">**Unikatowy** element w schemacie określa, że dla wszystkich elementów **klientów** w wystąpieniu dokumentu wartość elementu podrzędnego **CustomerID** musi być unikatowa.</span><span class="sxs-lookup"><span data-stu-id="9e940-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="9e940-115">Podczas kompilowania **zestawu danych**proces mapowania odczytuje ten schemat i generuje poniższą tabelę:</span><span class="sxs-lookup"><span data-stu-id="9e940-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="9e940-116">Proces mapowania powoduje także utworzenie unikatowego ograniczenia kolumny **CustomerID** , jak pokazano w poniższym **zestawie danych**.</span><span class="sxs-lookup"><span data-stu-id="9e940-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="9e940-117">(Dla uproszczenia są wyświetlane tylko odpowiednie właściwości.)</span><span class="sxs-lookup"><span data-stu-id="9e940-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="9e940-118">W wygenerowanym **zestawie danych** Właściwość **IsPrimaryKey** jest ustawiona na **wartość false** dla ograniczenia UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="9e940-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="9e940-119">Właściwość **Unique** kolumny wskazuje, że wartości kolumny **CustomerID** muszą być unikatowe (ale mogą być odwołaniem null, jak określono przez właściwość **AllowDBNull** kolumny).</span><span class="sxs-lookup"><span data-stu-id="9e940-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="9e940-120">Jeśli zmodyfikujesz schemat i ustawisz opcjonalną wartość atrybutu **msdata: PrimaryKey** na **true**, w tabeli zostanie utworzone ograniczenie UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="9e940-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="9e940-121">Właściwość Column **AllowDBNull** jest ustawiona na **false**, a właściwość **IsPrimaryKey** ograniczenia ma **wartość true**, co sprawia, że kolumna klucza podstawowego zostanie określona **jako kolumna.**</span><span class="sxs-lookup"><span data-stu-id="9e940-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="9e940-122">Można określić unikatowe ograniczenie kombinacji elementów lub atrybutów w schemacie XML.</span><span class="sxs-lookup"><span data-stu-id="9e940-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="9e940-123">W poniższym przykładzie pokazano, jak określić, że kombinacja wartości **CustomerID** i **NazwaFirmy** musi być unikatowa dla wszystkich **klientów** w dowolnym wystąpieniu, dodając inny element **xs: Field** w schemacie.</span><span class="sxs-lookup"><span data-stu-id="9e940-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="9e940-124">Jest to ograniczenie, które jest tworzone w powstałym **zestawie danych**.</span><span class="sxs-lookup"><span data-stu-id="9e940-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e940-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9e940-125">See also</span></span>

- [<span data-ttu-id="9e940-126">Mapowanie ograniczeń schematu XML (XSD) na ograniczenia elementu DataSet</span><span class="sxs-lookup"><span data-stu-id="9e940-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="9e940-127">Generowanie relacji elementu DataSet na podstawie schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="9e940-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="9e940-128">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e940-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
