---
title: Porównywanie obiektów przy użyciu tabeli XmlNameTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
ms.openlocfilehash: 5e0f5de6fd956bcaaf30b592e04c432a5f824c52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734104"
---
# <a name="object-comparison-using-xmlnametable"></a>Porównywanie obiektów przy użyciu tabeli XmlNameTable

Element **XmlDocuments**, po utworzeniu, ma tabelę nazw utworzoną dla tego dokumentu. Gdy XML jest ładowany do dokumentu lub są tworzone nowe elementy lub atrybuty, nazwy atrybutów i elementów są umieszczane w **XmlNameTable**. Można również utworzyć **XmlDocument** przy użyciu istniejącego **NameTable** z innego dokumentu. Gdy **dokumenty XmlDocument** są tworzone za pomocą konstruktora, który przyjmuje parametr **XmlNameTable** , dokument ma dostęp do nazw węzłów, przestrzeni nazw i prefiksów już przechowywanych w **XmlNameTable**. Niezależnie od sposobu ładowania tabeli nazw do nazw, gdy nazwy są przechowywane w tabeli, nazwy można porównać szybko przy użyciu porównania obiektów zamiast porównywania ciągów. Ciągi można także dodawać do tabeli nazw przy użyciu <xref:System.Xml.NameTable.Add%2A> . Poniższy przykład kodu przedstawia utworzoną tabelę nazw **i ciąg ciągu, który jest** dodawany do tabeli. Po tym elemencie **XmlDocument** zostanie utworzony przy użyciu tej tabeli, a nazwy elementów i atrybutów w **Myfile.xml** są dodawane do istniejącej tabeli nazw.  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 Poniższy przykład kodu pokazuje Tworzenie dokumentu, dwa nowe elementy dodawane do dokumentu, które również dodaje je do tabeli nazw dokumentów i porównanie obiektów dla nazw.  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 Powyższy scenariusz tabeli nazw przekazaną między dwoma dokumentami jest typowy, gdy ten sam typ dokumentu jest przetwarzany wielokrotnie, na przykład w kolejności dokumentów w witrynie handlu elektronicznego, który jest zgodny ze schematem języka definicji schematu XML (XSD) lub definicją typu dokumentu (DTD), a te same ciągi są powtórzone. Korzystanie z tej samej tabeli nazw zapewnia poprawę wydajności, ponieważ ta sama nazwa elementu występuje w wielu dokumentach.  
  
## <a name="see-also"></a>Zobacz także

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
