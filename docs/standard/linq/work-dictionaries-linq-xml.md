---
title: Jak korzystać ze słowników przy użyciu LINQ to XML-LINQ to XML
description: Można przekonwertować wiele rodzajów struktur danych na format XML i przekonwertować XML na struktury. Oto przykład, który konwertuje ogólny słownik do formatu XML i z powrotem.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 9f6304dde828b3269f1cf369c3a6f14368676a48
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554487"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml"></a>Praca ze słownikami przy użyciu LINQ to XML

Często wygodnie jest skonwertować struktury danych różnych rodzajów na XML, a następnie z XML do innych struktur danych. W tym artykule przedstawiono konwersję <xref:System.Collections.Generic.Dictionary%602> do formatu XML i z powrotem.

## <a name="example-create-a-dictionary-and-convert-its-contents-to-xml"></a>Przykład: Utwórz słownik i przekonwertuj jego zawartość na XML

Ten pierwszy przykład tworzy <xref:System.Collections.Generic.Dictionary%602> , a następnie konwertuje go na XML.

Ta wersja języka C# w tym przykładzie używa formularza konstrukcji funkcjonalnej, w którym zapytania projektują nowe <xref:System.Xml.Linq.XElement> obiekty, a wynikowa kolekcja jest przenoszona jako argument do konstruktora <xref:System.Xml.Linq.XElement> obiektu głównego.

Wersja Visual Basic używa literałów XML i zapytania w wyrażeniu osadzonym. Zapytanie projektuje nowe <xref:System.Xml.Linq.XElement> obiekty, które następnie staną się nową zawartością dla `Root` <xref:System.Xml.Linq.XElement> obiektu.

```csharp
Dictionary<string, string> dict = new Dictionary<string, string>();
dict.Add("Child1", "Value1");
dict.Add("Child2", "Value2");
dict.Add("Child3", "Value3");
dict.Add("Child4", "Value4");
XElement root = new XElement("Root",
    from keyValue in dict
    select new XElement(keyValue.Key, keyValue.Value)
);
Console.WriteLine(root);
```

```vb
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()
dict.Add("Child1", "Value1")
dict.Add("Child2", "Value2")
dict.Add("Child3", "Value3")
dict.Add("Child4", "Value4")
Dim root As XElement = _
    <Root>
        <%= From keyValue In dict _
            Select New XElement(keyValue.Key, keyValue.Value) %>
    </Root>
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child1>Value1</Child1>
  <Child2>Value2</Child2>
  <Child3>Value3</Child3>
  <Child4>Value4</Child4>
</Root>
```

## <a name="example-create-a-dictionary-and-load-it-from-xml-data"></a>Przykład: tworzenie słownika i ładowanie go z danych XML

Następny przykład tworzy ładujący słownik ładuje go z danych XML.

```csharp
XElement root = new XElement("Root",
    new XElement("Child1", "Value1"),
    new XElement("Child2", "Value2"),
    new XElement("Child3", "Value3"),
    new XElement("Child4", "Value4")
);

Dictionary<string, string> dict = new Dictionary<string, string>();
foreach (XElement el in root.Elements())
    dict.Add(el.Name.LocalName, el.Value);
foreach (string str in dict.Keys)
    Console.WriteLine("{0}:{1}", str, dict[str]);
```

```vb
Dim root As XElement = _
        <Root>
            <Child1>Value1</Child1>
            <Child2>Value2</Child2>
            <Child3>Value3</Child3>
            <Child4>Value4</Child4>
        </Root>

Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)
For Each el As XElement In root.Elements
    dict.Add(el.Name.LocalName, el.Value)
Next
For Each str As String In dict.Keys
    Console.WriteLine("{0}:{1}", str, dict(str))
Next
```

Ten przykład generuje następujące wyniki:

```output
Child1:Value1
Child2:Value2
Child3:Value3
Child4:Value4
```

## <a name="see-also"></a>Zobacz także

- [Operacje projekcji (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
