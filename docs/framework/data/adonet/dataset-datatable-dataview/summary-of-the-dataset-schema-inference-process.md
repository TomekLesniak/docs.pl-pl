---
title: Podsumowanie procesu wnioskowania schematu elementu DataSet
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 8d517487b96aa7f204ea9f25d326500db7df413a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198512"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Podsumowanie procesu wnioskowania schematu elementu DataSet

Proces wnioskowania najpierw określa, z dokumentu XML, które elementy zostaną wywnioskowane jako tabele. W pozostałej postaci kodu XML proces wnioskowania określa kolumny dla tych tabel. W przypadku zagnieżdżonych tabel proces wnioskowania generuje zagnieżdżone <xref:System.Data.DataRelation> i <xref:System.Data.ForeignKeyConstraint> obiekty.  
  
 Poniżej przedstawiono krótkie podsumowanie reguł wnioskowania:  
  
- Elementy, które mają atrybuty są wywnioskowane jako tabele.  
  
- Elementy, które mają elementy podrzędne są wywnioskowane jako tabele.  
  
- Elementy, które powtarzają się, są wywnioskowane jako jedna tabela.  
  
- Jeśli dokument lub element główny nie ma żadnych atrybutów i żadne elementy podrzędne, które zostałyby wywnioskowane jako kolumny, zostanie wywnioskowane jako <xref:System.Data.DataSet> . W przeciwnym razie element dokumentu jest wywnioskowany jako tabela.  
  
- Atrybuty są wywnioskowane jako kolumny.  
  
- Elementy, które nie mają atrybutów ani elementów podrzędnych, i które nie powtarzają się, są wywnioskowane jako kolumny.  
  
- W przypadku elementów, które są wywnioskowane jako zagnieżdżone tabele w innych elementach, które są również wywnioskowane jako tabele, zagnieżdżona **relacja** między dwiema tabelami zostanie utworzona. Nowa kolumna klucza podstawowego o nazwie **TableName_Id** jest dodawana do obu tabel i używana przez **relację**danych. **Element ForeignKeyConstraint** jest tworzony między dwiema tabelami przy użyciu kolumny **TableName_Id** .  
  
- Dla elementów, które są wywnioskowane jako tabele i które zawierają tekst, ale nie zawierają elementów podrzędnych, Nowa kolumna o nazwie **TableName_Text** jest tworzona dla tekstu każdego elementu. Jeśli element jest wywnioskowany jako tabela i zawiera tekst, ale również zawiera elementy podrzędne, tekst jest ignorowany.  
  
## <a name="see-also"></a>Zobacz też

- [Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML](inferring-dataset-relational-structure-from-xml.md)
- [Ładowanie elementu DataSet z pliku XML](loading-a-dataset-from-xml.md)
- [Ładowanie informacji o schemacie elementu DataSet z pliku XML](loading-dataset-schema-information-from-xml.md)
- [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
