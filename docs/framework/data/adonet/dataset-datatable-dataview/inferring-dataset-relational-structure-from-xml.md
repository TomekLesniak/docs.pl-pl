---
title: Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: fca50491120346dea3e09c82324225f2114380fc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177582"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML

Struktura relacyjna (lub schemat) składa <xref:System.Data.DataSet> się z tabel, kolumn, ograniczeń i relacji. Podczas ładowania <xref:System.Data.DataSet> z pliku XML schemat może być wstępnie zdefiniowany lub można go utworzyć, jawnie lub przez wnioskowanie, z ładującego kodu XML. Aby uzyskać więcej informacji na temat ładowania schematu i zawartości <xref:System.Data.DataSet> z pliku XML, zobacz [Ładowanie zestawu danych z XML](loading-a-dataset-from-xml.md) i [ładowanie informacji o schemacie zestawu danych z pliku XML](loading-dataset-schema-information-from-xml.md).  
  
 Jeśli schemat elementu <xref:System.Data.DataSet> jest tworzony na podstawie kodu XML, preferowaną metodą jest jawne określenie schematu przy użyciu języka definicji schematu XML (XSD) (zgodnie z opisem w temacie [pochodny struktura zestawu danych ze schematu XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) lub danych XML (XDR). Jeśli w kodzie XML nie jest dostępny żaden schemat XML ani schemat XDR, schemat <xref:System.Data.DataSet> można wywnioskować na podstawie struktury elementów i atrybutów XML.  
  
 W tej sekcji opisano reguły <xref:System.Data.DataSet> wnioskowania schematu przez pokazanie elementów i atrybutów XML oraz ich struktury, a następnie wywnioskowany <xref:System.Data.DataSet> schemat.  
  
 Nie wszystkie atrybuty obecne w dokumencie XML powinny być zawarte w procesie wnioskowania. Atrybuty kwalifikowane z przestrzenią nazw mogą zawierać metadane, które są ważne dla dokumentu XML, ale nie dla <xref:System.Data.DataSet> schematu. Za pomocą <xref:System.Data.DataSet.InferXmlSchema%2A> , można określić obszary nazw, które mają być ignorowane podczas procesu wnioskowania. Aby uzyskać więcej informacji, zobacz [ładowanie informacji o schemacie zestawu danych z pliku XML](loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Podsumowanie procesu wnioskowania schematu elementu DataSet](summary-of-the-dataset-schema-inference-process.md)  
 Zawiera ogólne podsumowanie reguł dotyczących wywnioskowania schematu <xref:System.Data.DataSet> z pliku XML.  
  
 [Wnioskowanie tabel](inferring-tables.md)  
 Opisuje elementy XML, które są wywnioskowane jako tabele w <xref:System.Data.DataSet> .  
  
 [Wnioskowanie kolumn](inferring-columns.md)  
 Opisuje elementy XML i atrybuty, które są wywnioskowane jako kolumny tabeli.  
  
 [Wnioskowanie relacji](inferring-relationships.md)  
 Opisuje <xref:System.Data.DataRelation> obiekty i <xref:System.Data.ForeignKeyConstraint> utworzone dla zagnieżdżonych, wywnioskowanych tabel.  
  
 [Wnioskowanie tekstu elementu](inferring-element-text.md)  
 Opisuje kolumny, które są tworzone dla tekstu w elementach XML, i wyjaśnia, kiedy tekst w elementach XML jest ignorowany.  
  
 [Ograniczenia wnioskowania](inference-limitations.md)  
 W tym artykule omówiono ograniczenia dotyczące wnioskowania dotyczącego schematu.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Używanie języka XML w elemencie DataSet](using-xml-in-a-dataset.md)  
 Opisuje, jak <xref:System.Data.DataSet> obiekt współdziała z danymi XML.  
  
 [Pobieranie relacyjnej struktury elementu DataSet ze schematu XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Opisuje strukturę relacyjną lub schemat, <xref:System.Data.DataSet> który jest tworzony na podstawie schematu definicji schematu XML (XSD).  
  
 [Omówienie ADO.NET](../ado-net-overview.md)  
 Opisuje architekturę i składniki ADO.NET oraz sposób ich używania do uzyskiwania dostępu do istniejących źródeł danych i zarządzania danymi aplikacji.  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie ADO.NET](../ado-net-overview.md)
