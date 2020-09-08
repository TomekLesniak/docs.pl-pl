---
title: Porównanie XPath i LINQ to XML LINQ to XML
description: Zapytania XPath i LINQ to XML mogą wykonywać zapytania dotyczące drzew XML. W tych artykułach porównano dwie opcje i znajduje się LINQ to XML zapytań, które mają być w całości, bardziej wydajne, uniwersalne, szybsze, bezpieczniejsze i wygodniejsze.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: b98651ffd7e0df0057164f40bedbc43d654d8c81
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553400"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Porównanie metody XPath i LINQ to XML

Wyrażenia XPath i LINQ to XML są podobne na kilka sposobów. Oba te funkcje mogą służyć do wykonywania zapytań w drzewie XML, zwracając takie wyniki jako kolekcja elementów, Kolekcja atrybutów, kolekcja węzłów lub wartość elementu lub atrybutu. Istnieją jednak znaczące różnice między tymi dwiema opcjami.

## <a name="differences-between-xpath-and-linq-to-xml"></a>Różnice między XPath i LINQ to XML

Wyrażenie XPath nie zezwala na projekcję nowych typów. Można zwrócić kolekcje węzłów tylko z drzewa, podczas gdy LINQ to XML może wykonać zapytanie i projektować obiekt Graph lub drzewo XML w nowym kształcie. Zapytania LINQ to XML mogą wykonywać wiele więcej niż wyrażenia XPath.

Wyrażenia XPath istnieją w izolacji w ciągu. Kompilator języka C# nie może pomóc w analizie wyrażenia XPath w czasie kompilacji. Z kolei LINQ to XML zapytania są analizowane i kompilowane przez kompilator języka C#. Kompilator może przechwycić wiele błędów zapytań.

Wyniki XPath nie są jednoznacznie wpisane. W wielu okolicznościach wynik oceny wyrażenia XPath jest obiektem, a programista może określić właściwy typ i rzutować wynik odpowiednio do potrzeb. Z kolei, projekcje z kwerendy LINQ to XML są jednoznacznie wpisane.

## <a name="result-ordering"></a>Porządkowanie wyników

Zalecenie XPath 1,0 stwierdza, że kolekcja będąca wynikiem oceny wyrażenia XPath jest nieuporządkowana.

Jednak podczas iteracji w kolekcji zwróconej przez LINQ to XML metodę osi XPath węzły w kolekcji są zwracane w kolejności dokumentu. Jest to przypadek, nawet w przypadku uzyskiwania dostępu do osi XPath, gdzie predykaty są wyrażane w postaci odwrotnej kolejności dokumentu, takiej jak `preceding` i `preceding-sibling` .

Z kolei większość osi LINQ to XML zwraca kolekcje w kolejności dokumentu. Jednak dwie z nich <xref:System.Xml.Linq.XNode.Ancestors%2A> i <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A> , zwracają kolekcje w kolejności wycofywania dokumentu. Poniższa tabela zawiera Wyliczenie osi i wskazuje kolejność kolekcji dla każdej z nich:

|Oś LINQ to XML|Zamawianie|
|----------------------|--------------|
|XContainer.DescendantNodes|Kolejność dokumentów|
|XContainer. Descendants|Kolejność dokumentów|
|XContainer. elementy|Kolejność dokumentów|
|XContainer. węzły|Kolejność dokumentów|
|XContainer.NodesAfterSelf|Kolejność dokumentów|
|XContainer.NodesBeforeSelf|Kolejność dokumentów|
|XElement. AncestorsAndSelf|Zamówienie odwrócenia dokumentu|
|XElement. Attributes|Kolejność dokumentów|
|XElement. DescendantNodesAndSelf|Kolejność dokumentów|
|XElement. DescendantsAndSelf|Kolejność dokumentów|
|XNode. przodków|Zamówienie odwrócenia dokumentu|
|XNode.ElementsAfterSelf|Kolejność dokumentów|
|XNode.ElementsBeforeSelf|Kolejność dokumentów|
|XNode.NodesAfterSelf|Kolejność dokumentów|
|XNode.NodesBeforeSelf|Kolejność dokumentów|

## <a name="positional-predicates"></a>Predykaty pozycyjne

W wyrażeniu XPath predykaty pozycyjne są wyrażane w zakresie kolejności dokumentu dla wielu osi, ale są wyrażane w kolejności odwrotnego dokumentu dla odwróconych osi. Odwrotne osie to: `preceding` , `preceding-sibling` , `ancestor` , i `ancestor-or-self` . Na przykład wyrażenie XPath `preceding-sibling::*[1]` zwraca bezpośrednio poprzedni element równorzędny. Dzieje się tak, mimo że końcowy zestaw wyników jest przedstawiony w kolejności dokumentu.

Z kolei wszystkie predykaty pozycyjne w LINQ to XML są zawsze wyrażane w warunkach kolejności osi. Na przykład `anElement.ElementsBeforeSelf().ElementAt(0)` zwraca pierwszy element podrzędny obiektu nadrzędnego z zapytania elementu, a nie bezpośrednio poprzedzającego element równorzędny. Inny przykład: `anElement.Ancestors().ElementAt(0)` zwraca element nadrzędny.

Aby znaleźć bezpośrednio poprzedzający element w LINQ to XML, należy napisać następujące wyrażenie:

```csharp
ElementsBeforeSelf().Last()
```

```vb
ElementsBeforeSelf().Last()
```

## <a name="performance-differences"></a>Różnice w wydajności

Zapytania XPath korzystające z funkcji XPath w LINQ to XML będą wolniejsze niż LINQ to XML zapytań.

## <a name="comparison-of-composition"></a>Porównanie kompozycji

Kompozycja LINQ to XML zapytania jest podobna do składowej wyrażenia XPath, ale składnia jest bardzo inna.

Na przykład jeśli masz element w zmiennej o nazwie `customers` i chcesz znaleźć element grandchild o nazwie `CompanyName` pod wszystkimi elementami podrzędnymi o nazwie `Customer` , napisz wyrażenie XPath:

```csharp
customers.XPathSelectElements("./Customer/CompanyName")
```

```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

Odpowiednik kwerendy LINQ to XML jest:

```csharp
customers.Elements("Customer").Elements("CompanyName")
```

```vb
customers.Elements("Customer").Elements("CompanyName")
```

Istnieją podobne równoległości dla każdej z osi XPath.

|Oś XPath|Oś LINQ to XML|
|----------------|----------------------|
|element podrzędny (oś domyślna)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|
|Nadrzędne (..)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|
|oś atrybutów (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> lub<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|
|oś nadrzędna|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|
|obiekt nadrzędny lub samosamej osi|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|
|oś elementu podrzędnego (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> lub<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|
|elementy podrzędne lub samodzielne|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> lub<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|
|poniżej — element równorzędny|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> lub<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|
|Poprzedni element równorzędny|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> lub<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|
|dodaje|Brak bezpośredniego odpowiednika.|
|licencyjn|Brak bezpośredniego odpowiednika.|
