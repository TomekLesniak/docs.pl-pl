---
title: Wnioskowanie relacji
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177569"
---
# <a name="inferring-relationships"></a>Wnioskowanie relacji

Jeśli element, który jest wywnioskowany jako tabela, ma element podrzędny, który jest również wywnioskowany jako tabela, <xref:System.Data.DataRelation> zostanie utworzony między dwiema tabelami. Nowa kolumna o nazwie **ParentTableName_Id** zostanie dodana do tabeli utworzonej dla elementu nadrzędnego, a tabela utworzona dla elementu podrzędnego. Właściwość **ColumnMapping** tej kolumny tożsamości zostanie ustawiona na wartość **MappingType. Hidden**. Kolumna będzie przerastać klucz podstawowy dla tabeli nadrzędnej i będzie używana dla **relacji** między tymi dwiema tabelami. Typem danych kolumny dodanej tożsamości będzie **System. Int32**, w przeciwieństwie do typu danych wszystkich innych wywnioskowanych kolumn, które jest **System. String**. Element <xref:System.Data.ForeignKeyConstraint> with **DeleteRule**  =  **Cascade** również zostanie utworzony przy użyciu nowej kolumny w tabeli nadrzędnej i podrzędnej.  
  
 Rozważmy na przykład następujący kod XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Proces wnioskowania spowoduje utworzenie dwóch tabel: **element1** i **ChildElement1**.  
  
 Tabela **element1** będzie miała dwie kolumny: **Element1_Id** i **ChildElement2**. Właściwość **ColumnMapping** kolumny **Element1_Id** zostanie ustawiona na wartość **MappingType. Hidden**. Właściwość **ColumnMapping** kolumny **ChildElement2** zostanie ustawiona na wartość **MappingType. element**. Kolumna **Element1_Id** zostanie ustawiona jako klucz podstawowy tabeli **element1** .  
  
 Tabela **ChildElement1** będzie miała trzy kolumny: **attr1**, **attr2** i **Element1_Id**. Właściwość **ColumnMapping** dla kolumn **attr1** i **Attr2** zostanie ustawiona na wartość **MappingType. Attribute**. Właściwość **ColumnMapping** kolumny **Element1_Id** zostanie ustawiona na wartość **MappingType. Hidden**.  
  
 **Relacja** i **element ForeignKeyConstraint** zostanie utworzona przy użyciu kolumn **Element1_Id** z obu tabel.  
  
 **Zestaw danych:** DocumentElement  
  
 **Tabela:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabela:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|sekwencj|wartość2|0|  
  
 **Relacja** : Element1_ChildElement1  
  
 **Element nadrzędny:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **Elementy podrzędne:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Zagnieżdżone:** Oznacza  
  
 **Element ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Kolumna:** Element1_Id  
  
 **Element nadrzędny:** Element1  
  
 **Elementy podrzędne:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** Dawaj  
  
## <a name="see-also"></a>Zobacz też

- [Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML](inferring-dataset-relational-structure-from-xml.md)
- [Ładowanie elementu DataSet z pliku XML](loading-a-dataset-from-xml.md)
- [Ładowanie informacji o schemacie elementu DataSet z pliku XML](loading-dataset-schema-information-from-xml.md)
- [Zagnieżdżanie elementów DataRelation](nesting-datarelations.md)
- [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
