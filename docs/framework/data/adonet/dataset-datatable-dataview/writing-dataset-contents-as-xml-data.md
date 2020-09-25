---
title: Zapisywanie zawartości elementu DataSet jako danych XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: c8a5c747e4ec60fcb97edf631aa3a0ae184ffec5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173721"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Zapisywanie zawartości elementu DataSet jako danych XML

W ADO.NET można napisać reprezentację XML obiektu <xref:System.Data.DataSet> , z lub bez jego schematu. Jeśli informacje o schemacie są dołączone do kodu XML, są zapisywane przy użyciu języka definicji schematu XML (XSD). Schemat zawiera definicje tabeli, <xref:System.Data.DataSet> a także relacje i definicje ograniczeń.  
  
 Gdy obiekt <xref:System.Data.DataSet> jest zapisywana jako dane XML, wiersze w programie <xref:System.Data.DataSet> są zapisywane w ich bieżących wersjach. Jednak <xref:System.Data.DataSet> może być również zapisany jako DiffGram, tak aby wszystkie bieżące i oryginalne wartości wierszy były uwzględniane.  
  
 Reprezentacja XML <xref:System.Data.DataSet> można zapisać do pliku, strumienia, elementu **XmlWriter**lub ciągu. Te opcje zapewniają dużą elastyczność w zakresie transportu reprezentacji XML <xref:System.Data.DataSet> . Aby uzyskać reprezentację XML <xref:System.Data.DataSet> jako ciąg, użyj metody **GetXml —** , jak pokazano w poniższym przykładzie.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml —** zwraca reprezentację XML <xref:System.Data.DataSet> bez informacji o schemacie. Aby zapisać informacje o schemacie z <xref:System.Data.DataSet> (jako schemat XML) w ciągu, użyj elementu **GetXmlSchema**.  
  
 Aby napisać <xref:System.Data.DataSet> plik, strumień lub **XmlWriter**, użyj metody **WriteXml** . Pierwszym parametrem przekazywanym do **WriteXml** jest miejsce docelowe danych wyjściowych XML. Na przykład Przekaż ciąg zawierający nazwę pliku, obiekt **System. IO. TextWriter** i tak dalej. Aby określić sposób zapisywania danych wyjściowych XML, można przekazać opcjonalny drugi parametr **XmlWriteMode** .  
  
 W poniższej tabeli przedstawiono opcje elementu **XmlWriteMode**.  
  
|XmlWriteMode — opcja|Opis|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Zapisuje bieżącą zawartość <xref:System.Data.DataSet> jako dane XML, bez schematu XML. Jest to opcja domyślna.|  
|**WriteSchema**|Zapisuje bieżącą zawartość <xref:System.Data.DataSet> jako dane XML przy użyciu struktury relacyjnej jako wbudowanego schematu XML.|  
|**Formacie**|Zapisuje cały <xref:System.Data.DataSet> element w formacie DiffGram, w tym pierwotne i bieżące wartości. Aby uzyskać więcej informacji, zobacz [DiffGrams](diffgrams.md).|  
  
 Gdy piszesz reprezentację XML zawierającą <xref:System.Data.DataSet> obiekty **DataRelation** , najprawdopodobniej chcesz, aby otrzymany kod XML miał wszystkie wiersze podrzędne każdej relacji zagnieżdżonej w pokrewnych elementach nadrzędnych. Aby to osiągnąć, należy ustawić właściwość **zagnieżdżoną** elementu **DataRelation** na **wartość true** , gdy dodasz **relację** do obiektu <xref:System.Data.DataSet> . Aby uzyskać więcej informacji, zobacz [zagnieżdżanie relacji](nesting-datarelations.md)danych.  
  
 Poniżej przedstawiono dwa przykłady sposobu pisania reprezentacji XML <xref:System.Data.DataSet> do pliku. Pierwszy przykład przekazuje nazwę pliku XML w postaci ciągu do **WriteXml**. Drugi przykład przekazuje obiekt **System. IO. StreamWriter —** .
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Mapowanie kolumn do elementów XML, atrybutów i tekstu  

 Można określić sposób, w jaki kolumna tabeli jest reprezentowana w kodzie XML przy użyciu właściwości **ColumnMapping** obiektu **DataColumn** . W poniższej tabeli przedstawiono różne wartości **mapowaniatype** dla właściwości **ColumnMapping** kolumny tabeli oraz otrzymany kod XML.  
  
|Wartość MappingType|Opis|  
|-----------------------|-----------------|  
|**Postaci**|Jest to opcja domyślna. Kolumna jest zapisywana jako element XML, gdzie ColumnName jest nazwą elementu, a zawartość kolumny jest zapisywana jako tekst elementu. Na przykład:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Atrybut**|Kolumna jest zapisywana jako atrybut XML elementu XML dla bieżącego wiersza, gdzie ColumnName jest nazwą atrybutu, a zawartość kolumny jest zapisywana jako wartość atrybutu. Na przykład:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Zawartość kolumny jest zapisywana jako tekst w elemencie XML dla bieżącego wiersza. Na przykład:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Należy zauważyć, że nie można ustawić elementu **SimpleContent** dla kolumny tabeli, która zawiera kolumny **elementów** lub relacje zagnieżdżone.|  
|**Ukryte**|Kolumna nie jest zapisywana w danych wyjściowych XML.|  
  
## <a name="see-also"></a>Zobacz też

- [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)
- [Elementy DiffGram](diffgrams.md)
- [Zagnieżdżanie elementów DataRelation](nesting-datarelations.md)
- [Zapisywanie informacji o schemacie elementu DataSet jako pliku XSD](writing-dataset-schema-information-as-xsd.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
