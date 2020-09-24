---
title: Wnioskowanie kolumn
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 45d27b78b5d83d333c16192e172e7b7e3dd88c10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164704"
---
# <a name="inferring-columns"></a>Wnioskowanie kolumn

Po ustaleniu ADO.NET z dokumentu XML, który elementy do wnioskowania jako tabele dla a <xref:System.Data.DataSet> , następnie wnioskuje kolumny dla tych tabel. W ADO.NET 2,0 wprowadzono nowy aparat wnioskowania schematu, który wnioskuje typ danych o jednoznacznie określonym typie dla każdego elementu **simpleType** . W poprzednich wersjach typ danych wywnioskowanego elementu **simpleType** miał zawsze wartość **XSD: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migracja i zgodność z poprzednimi wersjami  

 Metoda **ReadXml** przyjmuje argument typu **InferSchema**. Ten argument umożliwia określenie zachowania wnioskowania zgodnego z poprzednimi wersjami. Dostępne wartości wyliczenia **InferSchema** są przedstawione w poniższej tabeli.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Zapewnia zgodność z poprzednimi wersjami przez zawsze wywnioskowanie typu prostego jako <xref:System.String> .  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Wnioskuje typ danych o jednoznacznie określonym typie. Zgłasza wyjątek, jeśli jest używany z <xref:System.Data.DataTable> .  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignoruje wszystkie wbudowane schemat i odczytuje dane w istniejącym <xref:System.Data.DataSet> schemacie.  
  
## <a name="attributes"></a>Atrybuty  

 Zgodnie z definicją w [tabelach odwołujących](inferring-tables.md)element z atrybutami zostanie wywnioskowany jako tabela. Atrybuty tego elementu zostaną następnie wywnioskowane jako kolumny dla tabeli. Właściwość **ColumnMapping** kolumn zostanie ustawiona na wartość **MappingType. Attribute**, aby upewnić się, że nazwy kolumn będą zapisywane jako atrybuty, jeśli schemat jest zapisywana z powrotem do kodu XML. Wartości atrybutów są przechowywane w wierszu w tabeli. Rozważmy na przykład następujący kod XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Proces wnioskowania spowoduje utworzenie tabeli o nazwie **element1** z dwiema kolumnami, **attr1** i **attr2**. Właściwość **ColumnMapping** obu kolumn zostanie ustawiona na wartość **MappingType. Attribute**.  
  
 **Zestaw danych:** DocumentElement  
  
 **Tabela:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|sekwencj|wartość2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elementy bez atrybutów lub elementów podrzędnych  

 Jeśli element nie ma elementów podrzędnych ani atrybutów, zostanie wywnioskowany jako kolumna. Właściwość **ColumnMapping** kolumny zostanie ustawiona na wartość **MappingType. element**. Tekst dla elementów podrzędnych jest przechowywany w wierszu w tabeli. Rozważmy na przykład następujący kod XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Proces wnioskowania spowoduje utworzenie tabeli o nazwie **element1** z dwiema kolumnami, **ChildElement1** i **ChildElement2**. Właściwość **ColumnMapping** obu kolumn zostanie ustawiona na wartość **MappingType. element**.  
  
 **Zestaw danych:** DocumentElement  
  
 **Tabela:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Organizacji1|Text2|  
  
## <a name="see-also"></a>Zobacz też

- [Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML](inferring-dataset-relational-structure-from-xml.md)
- [Ładowanie elementu DataSet z pliku XML](loading-a-dataset-from-xml.md)
- [Ładowanie informacji o schemacie elementu DataSet z pliku XML](loading-dataset-schema-information-from-xml.md)
- [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
