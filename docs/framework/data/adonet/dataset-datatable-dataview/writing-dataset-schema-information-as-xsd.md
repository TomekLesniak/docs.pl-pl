---
title: Zapisywanie informacji o schemacie elementu DataSet jako pliku XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173734"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="9ca4d-102">Zapisywanie informacji o schemacie elementu DataSet jako pliku XSD</span><span class="sxs-lookup"><span data-stu-id="9ca4d-102">Writing DataSet Schema Information as XSD</span></span>

<span data-ttu-id="9ca4d-103">Można napisać schemat programu <xref:System.Data.DataSet> jako schemat języka definicji schematu XML (XSD), dzięki czemu można transportować go z lub bez powiązanych danych w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="9ca4d-104">Schemat XML można zapisać w pliku, strumieniu, a <xref:System.Xml.XmlWriter> lub ciągu; jest to przydatne w przypadku generowania **zestawu danych**o jednoznacznie określonym typie.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="9ca4d-105">Aby uzyskać więcej informacji na temat obiektów typu **zestaw danych** o jednoznacznie określonym typie, zobacz [zestawy danych z określonym typem](typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="9ca4d-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="9ca4d-106">Można określić sposób, w jaki kolumna tabeli jest reprezentowana w schemacie XML przy użyciu właściwości **ColumnMapping** <xref:System.Data.DataColumn> obiektu.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="9ca4d-107">Aby uzyskać więcej informacji, zobacz "Mapowanie kolumn do elementów XML, atrybutów i tekstu" w [treści zestawu danych jako dane XML](writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="9ca4d-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="9ca4d-108">Aby zapisać schemat **zestawu danych** jako schemat XML, do pliku, strumienia lub **XmlWriter**, użyj metody **WriteXmlSchema** **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="9ca4d-109">**WriteXmlSchema** przyjmuje jeden parametr, który określa miejsce docelowe uzyskanego schematu XML.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="9ca4d-110">Poniższy przykład kodu pokazuje, jak napisać schemat XML **zestawu danych** do pliku, przekazując ciąg zawierający nazwę pliku i <xref:System.IO.StreamWriter> obiekt.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="9ca4d-111">Aby uzyskać schemat **zestawu danych** i zapisać go jako ciąg schematu XML, należy **użyć metody GetXml,** jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ca4d-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ca4d-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9ca4d-112">See also</span></span>

- [<span data-ttu-id="9ca4d-113">Używanie języka XML w elemencie DataSet</span><span class="sxs-lookup"><span data-stu-id="9ca4d-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="9ca4d-114">Zapisywanie zawartości elementu DataSet jako danych XML</span><span class="sxs-lookup"><span data-stu-id="9ca4d-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="9ca4d-115">Typizowane elementy DataSet</span><span class="sxs-lookup"><span data-stu-id="9ca4d-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="9ca4d-116">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="9ca4d-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="9ca4d-117">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ca4d-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
