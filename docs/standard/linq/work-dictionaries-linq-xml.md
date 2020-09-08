---
title: Jak korzystać ze słowników przy użyciu LINQ to XML-LINQ to XML
description: Można przekonwertować wiele rodzajów struktur danych na format XML i przekonwertować XML na struktury. Oto przykład, który konwertuje ogólny słownik do formatu XML i z powrotem.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: ea61a79549488765526f45852dae7a4df7cacb64
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553216"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml"></a><span data-ttu-id="0ab79-104">Praca ze słownikami przy użyciu LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="0ab79-104">How to work with dictionaries using LINQ to XML</span></span>

<span data-ttu-id="0ab79-105">Często wygodnie jest skonwertować struktury danych różnych rodzajów na XML, a następnie z XML do innych struktur danych.</span><span class="sxs-lookup"><span data-stu-id="0ab79-105">It's often convenient to convert data structures of various kinds to XML, and then from XML to other data structures.</span></span> <span data-ttu-id="0ab79-106">W tym artykule przedstawiono konwersję <xref:System.Collections.Generic.Dictionary%602> do formatu XML i z powrotem.</span><span class="sxs-lookup"><span data-stu-id="0ab79-106">This article shows a conversion of a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>

## <a name="example-create-a-dictionary-and-convert-its-contents-to-xml"></a><span data-ttu-id="0ab79-107">Przykład: Utwórz słownik i przekonwertuj jego zawartość na XML</span><span class="sxs-lookup"><span data-stu-id="0ab79-107">Example: Create a Dictionary and convert its contents to XML</span></span>

<span data-ttu-id="0ab79-108">Ten pierwszy przykład tworzy <xref:System.Collections.Generic.Dictionary%602> , a następnie konwertuje go na XML.</span><span class="sxs-lookup"><span data-stu-id="0ab79-108">This first example creates a <xref:System.Collections.Generic.Dictionary%602>, and then converts it to XML.</span></span>

<span data-ttu-id="0ab79-109">Ta wersja języka C# w tym przykładzie używa formularza konstrukcji funkcjonalnej, w którym zapytania projektują nowe <xref:System.Xml.Linq.XElement> obiekty, a wynikowa kolekcja jest przenoszona jako argument do konstruktora <xref:System.Xml.Linq.XElement> obiektu głównego.</span><span class="sxs-lookup"><span data-stu-id="0ab79-109">This C# version of the example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>

<span data-ttu-id="0ab79-110">Wersja Visual Basic używa literałów XML i zapytania w wyrażeniu osadzonym.</span><span class="sxs-lookup"><span data-stu-id="0ab79-110">The Visual Basic version uses XML literals and a query in an embedded expression.</span></span> <span data-ttu-id="0ab79-111">Zapytanie projektuje nowe <xref:System.Xml.Linq.XElement> obiekty, które następnie staną się nową zawartością dla `Root` <xref:System.Xml.Linq.XElement> obiektu.</span><span class="sxs-lookup"><span data-stu-id="0ab79-111">The query projects new <xref:System.Xml.Linq.XElement> objects which then become the new content for the `Root` <xref:System.Xml.Linq.XElement> object.</span></span>

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

<span data-ttu-id="0ab79-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0ab79-112">This example produces the following output:</span></span>

```xml
<Root>
  <Child1>Value1</Child1>
  <Child2>Value2</Child2>
  <Child3>Value3</Child3>
  <Child4>Value4</Child4>
</Root>
```

## <a name="example-create-a-dictionary-and-load-it-from-xml-data"></a><span data-ttu-id="0ab79-113">Przykład: tworzenie słownika i ładowanie go z danych XML</span><span class="sxs-lookup"><span data-stu-id="0ab79-113">Example: Create a dictionary and load it from XML data</span></span>

<span data-ttu-id="0ab79-114">Następny przykład tworzy ładujący słownik ładuje go z danych XML.</span><span class="sxs-lookup"><span data-stu-id="0ab79-114">The next example creates a dictionary loads loads it from XML data.</span></span>

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

<span data-ttu-id="0ab79-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0ab79-115">This example produces the following output:</span></span>

```output
Child1:Value1
Child2:Value2
Child3:Value3
Child4:Value4
```

## <a name="see-also"></a><span data-ttu-id="0ab79-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ab79-116">See also</span></span>

- [<span data-ttu-id="0ab79-117">Projekcje i przekształcenia (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ab79-117">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
