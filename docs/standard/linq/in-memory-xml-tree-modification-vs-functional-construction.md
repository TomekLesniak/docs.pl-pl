---
title: Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna — LINQ to XML
description: Zobacz przykłady dwóch różnych metod modyfikowania drzew XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b5afc31d-a325-4ec6-bf17-0ff90a20ffca
ms.openlocfilehash: 71f76d12024bb07cf90df2299df14646ae271b47
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552972"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml"></a>Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna (LINQ to XML)

Modyfikowanie drzewa XML jest tradycyjnym podejściem do zmiany kształtu dokumentu XML. Typowa aplikacja ładuje dokument do magazynu danych, takiego jak DOM lub LINQ to XML; używa interfejsu programowania do wstawiania lub usuwania węzłów lub zmiany ich zawartości; a następnie zapisuje plik XML do pliku lub przesyła go za pośrednictwem sieci.

LINQ to XML zapewnia kolejną metodę, która jest przydatna w wielu scenariuszach: *konstrukcja funkcjonalna*. Konstrukcja funkcjonalna traktuje modyfikowanie danych jako problem transformacji, a nie jako szczegółowe manipulowanie magazynem danych. Jeśli możesz wykonać reprezentację danych i Przekształć ją efektywnie z jednego formularza na inny, wynik jest taki sam jak w przypadku, gdy został przestawiony jeden magazyn danych i manipulowanie nim w jakiś sposób, aby zastosować inny kształt. Najważniejszym podejściem do konstrukcji funkcjonalnej jest przekazanie wyników zapytań do <xref:System.Xml.Linq.XDocument> i <xref:System.Xml.Linq.XElement> konstruktorów.

W wielu przypadkach można napisać przekształcenie kod w ułamku czasu, jaki mógłby wykonać w celu manipulowania magazynem danych, a otrzymany kod jest bardziej niezawodny i łatwiejszy w obsłudze. W takich przypadkach, mimo że podejście przekształcenie może mieć większą moc obliczeniową, jest to bardziej efektywny sposób modyfikacji danych. Jeśli programista zna podejście funkcjonalne, kod wynikający z wielu przypadków jest łatwiejszy do zrozumienia i można łatwo znaleźć kod, który modyfikuje każdą część drzewa.

Podejście, gdzie modyfikujesz drzewo XML, jest bardziej znane dla wielu programistów modelu DOM, natomiast kod zapisany przy użyciu podejścia funkcjonalnego może wyglądać nieznajomo dla deweloperów, który nie rozumie tego podejścia. Jeśli konieczne jest tylko małe modyfikacje w dużym drzewie XML, podejście, w którym można modyfikować drzewo w wielu przypadkach, zajmie mniej czasu procesora.

W tym artykule przedstawiono przykłady obu tych metod. Załóżmy, że chcesz zmodyfikować następujący prosty dokument XML, aby atrybuty staną się elementami:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Root Data1="123" Data2="456">
  <Child1>Content</Child1>
</Root>
```

Pierwszy z poniższych przykładów używa tradycyjnego podejścia do modyfikacji w miejscu, a drugi używa podejścia konstruowania funkcjonalnego.

## <a name="example-transform-attributes-into-elements-with-the-traditional-in-place-approach"></a>Przykład: Przekształć atrybuty na elementy z tradycyjnym podejściem w miejscu

Można napisać kod proceduralny, aby utworzyć elementy z atrybutów, a następnie usunąć atrybuty w następujący sposób:

```csharp
XElement root = XElement.Load("Data.xml");
foreach (XAttribute att in root.Attributes()) {
    root.Add(new XElement(att.Name, (string)att));
}
root.Attributes().Remove();
Console.WriteLine(root);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
For Each att As XAttribute In root.Attributes()
    root.Add(New XElement(att.Name, att.Value))
Next
root.Attributes().Remove()
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child1>Content</Child1>
  <Data1>123</Data1>
  <Data2>456</Data2>
</Root>
```

## <a name="example-transform-attributes-into-elements-with-the-functional-construction-approach"></a>Przykład: Przekształć atrybuty na elementy z podejściem konstrukcja funkcjonalna

Z kolei podejście funkcjonalne obejmuje kod służący do tworzenia nowego drzewa, wybierania i wybierania elementów i atrybutów z drzewa źródłowego i przekształcania ich zgodnie z potrzebami, gdy są dodawane do nowego drzewa.

```csharp
XElement root = XElement.Load("Data.xml");
XElement newTree = new XElement("Root",
    root.Element("Child1"),
    from att in root.Attributes()
    select new XElement(att.Name, (string)att)
);
Console.WriteLine(newTree);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
Dim newTree As XElement = _
    <Root>
        <%= root.<Child1> %>
        <%= From att In root.Attributes() _
            Select New XElement(att.Name, att.Value) %>
    </Root>
Console.WriteLine(newTree)
```

Ten przykład wyprowadza ten sam kod XML jako pierwszy przykład. Należy jednak zauważyć, że w metodzie funkcjonalnej można zobaczyć uzyskaną strukturę nowego kodu XML. Można zobaczyć `Root` , jak utworzyć element, kod, który ściąga `Child1` element z drzewa źródłowego, oraz kod, który przekształca atrybuty z drzewa źródłowego do elementów w nowym drzewie.

Przykład funkcjonalny w tym przypadku nie jest krótszy ani łatwiejszy od pierwszego przykładu. Jeśli jednak w drzewie XML wprowadzono wiele zmian, podejście proceduralne staje się dość skomplikowane i dość obtuse. Natomiast w przypadku korzystania z podejścia funkcjonalnego nadal wystarczy utworzyć żądany kod XML, a następnie osadzić zapytania i wyrażenia, aby ściągnąć odpowiednią zawartość. Podejście funkcjonalne daje kod, który jest łatwiejszy w obsłudze.

Należy zauważyć, że w tym przypadku podejście funkcjonalne prawdopodobnie nie będzie działać w sposób niewidoczny, a także podejście do manipulowania drzewem. Główny problem polega na tym, że podejście funkcjonalne tworzy więcej obiektów krótkich. Jednak kompromis jest skuteczny, jeśli użycie podejścia funkcjonalnego pozwala zwiększyć produktywność programistyczną.

Jest to bardzo prosty przykład, ale służy do wyświetlania różnicy między dwoma podejściami. Podejście funkcjonalne daje większe korzyści produktywności związane z transformą większych dokumentów XML.
