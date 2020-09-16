---
title: Jak znaleźć elementy podrzędne na podstawie pozycji LINQ to XML
description: 'Dowiedz się, jak znaleźć elementy Znajdź na podstawie pozycji elementu. Pokazano trzy metody: jedna, która używa XPathEvaluate, dwóch, które używają kwerendy LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: 889e3dbac3acf229fd49422285d650fc13792521
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557122"
---
# <a name="how-to-find-child-elements-based-on-position-linq-to-xml"></a>Jak znaleźć elementy podrzędne na podstawie pozycji (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> Narzędzia do znajdowania elementów na podstawie pozycji elementu, na przykład w celu znalezienia drugiego elementu lub od trzeciego do piątego. Przedstawiono w nim również dwa sposoby używania zapytania LINQ to XML, aby wykonać to samo.

Istnieją dwa podejścia do zapisu tego LINQ to XML zapytania w sposób opóźniony. Można użyć <xref:System.Linq.Enumerable.Skip%2A> <xref:System.Linq.Enumerable.Take%2A> operatorów i lub użyć <xref:System.Linq.Enumerable.Where%2A> przeciążenia, które przyjmuje indeks. Używając <xref:System.Linq.Enumerable.Where%2A> przeciążenia, należy użyć wyrażenia lambda, które przyjmuje dwa argumenty. W poniższym przykładzie przedstawiono obie metody wyboru na podstawie pozycji.

## <a name="example-find-the-second-through-the-fourth-test-elements"></a>Przykład: Znajdź sekundę za pomocą czwartych `Test` elementów

Ten przykład wyszukuje sekundę za pomocą czwartego `Test` elementu w [przykładowym pliku XML: konfiguracji testu](sample-xml-file-test-configuration.md). Wynik jest kolekcją elementów.

Wyrażenie XPath ma wartość `Test[position() >= 2 and position() <= 4]` .

```csharp
XElement testCfg = XElement.Load("TestConfig.xml");

// LINQ to XML query
IEnumerable<XElement> list1 =
    testCfg
    .Elements("Test")
    .Skip(1)
    .Take(3);

// LINQ to XML query
IEnumerable<XElement> list2 =
    testCfg
    .Elements("Test")
    .Where((el, idx) => idx >= 1 && idx <= 3);

// XPath expression
IEnumerable<XElement> list3 =
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");

if (list1.Count() == list2.Count() &&
    list1.Count() == list3.Count() &&
    list1.Intersect(list2).Count() == list1.Count() &&
    list1.Intersect(list3).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim testCfg As XElement = XElement.Load("TestConfig.xml")

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = _
    testCfg.Elements("Test").Skip(1).Take(3)

'LINQ to XML query
Dim list2 As IEnumerable(Of XElement) = _
    testCfg.Elements("Test"). _
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)

' XPath expression
Dim list3 As IEnumerable(Of XElement) = _
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")

If list1.Count() = list2.Count() And _
       list1.Count() = list3.Count() And _
       list1.Intersect(list2).Count() = list1.Count() And _
       list1.Intersect(list3).Count() = list1.Count() Then

    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If

For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

Ten przykład generuje następujące wyniki:

```output
Results are identical
<Test TestId="0002" TestType="CMD">
  <Name>Find succeeding characters</Name>
  <CommandLine>Examp2.EXE</CommandLine>
  <Input>abc</Input>
  <Output>def</Output>
</Test>
<Test TestId="0003" TestType="GUI">
  <Name>Convert multiple numbers to strings</Name>
  <CommandLine>Examp2.EXE /Verbose</CommandLine>
  <Input>123</Input>
  <Output>One Two Three</Output>
</Test>
<Test TestId="0004" TestType="GUI">
  <Name>Find correlated key</Name>
  <CommandLine>Examp3.EXE</CommandLine>
  <Input>a1</Input>
  <Output>b1</Output>
</Test>
```

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
