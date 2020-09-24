---
title: Wnioskowanie tekstu elementu
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 7389e24f39902edf041c3cd3502303b17fd008ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164691"
---
# <a name="inferring-element-text"></a>Wnioskowanie tekstu elementu

Jeśli element zawiera tekst i nie ma żadnych elementów podrzędnych, które mają być wywnioskowane jako tabele (takie jak elementy z atrybutami lub powtarzalne elementy), Nowa kolumna o nazwie **TableName_Text** zostanie dodana do tabeli, która jest wywnioskowana dla elementu. Tekst zawarty w elemencie zostanie dodany do wiersza w tabeli i zapisany w nowej kolumnie. Właściwość **ColumnMapping** nowej kolumny zostanie ustawiona na wartość **MappingType. SimpleContent**.  
  
 Rozważmy na przykład następujący kod XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Proces wnioskowania spowoduje utworzenie tabeli o nazwie **element1** z dwiema kolumnami: **attr1** i **Element1_Text**. Właściwość **ColumnMapping** kolumny **attr1** zostanie ustawiona na wartość **MappingType. Attribute**. Właściwość **ColumnMapping** kolumny **Element1_Text** zostanie ustawiona na wartość **MappingType. SimpleContent**.  
  
 **Zestaw danych:** DocumentElement  
  
 **Tabela:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|sekwencj|Organizacji1|  
  
 Jeśli element zawiera tekst, ale również zawiera elementy podrzędne, które zawierają tekst, kolumna nie zostanie dodana do tabeli w celu przechowania tekstu zawartego w elemencie. Tekst zawarty w elemencie zostanie zignorowany, podczas gdy tekst w elementach podrzędnych zostanie uwzględniony w wierszu w tabeli. Rozważmy na przykład następujący kod XML.  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Proces wnioskowania spowoduje utworzenie tabeli o nazwie **element1** z jedną kolumną o nazwie **ChildElement1**. Tekst elementu **ChildElement1** zostanie uwzględniony w wierszu w tabeli. Drugi tekst zostanie zignorowany. Właściwość **ColumnMapping** kolumny **ChildElement1** zostanie ustawiona na wartość **MappingType. element**.  
  
 **Zestaw danych:** DocumentElement  
  
 **Tabela:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Zobacz też

- [Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML](inferring-dataset-relational-structure-from-xml.md)
- [Ładowanie elementu DataSet z pliku XML](loading-a-dataset-from-xml.md)
- [Ładowanie informacji o schemacie elementu DataSet z pliku XML](loading-dataset-schema-information-from-xml.md)
- [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
