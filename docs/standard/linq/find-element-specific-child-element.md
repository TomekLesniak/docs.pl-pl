---
title: Jak znaleźć element z określonym elementem podrzędnym LINQ to XML
description: Znajdź element, którego element podrzędny ma określoną wartość
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 2f97f920ce09222858a0a51eb52ffe0d58dba960
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678639"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-linq-to-xml"></a>Jak znaleźć element z określonym elementem podrzędnym (LINQ to XML)

W tym artykule pokazano, jak znaleźć element, którego element podrzędny ma określoną wartość.

## <a name="example-find-an-element-whose-child-element-has-a-specific-value"></a>Przykład: Znajdź element, którego element podrzędny ma określoną wartość

Przykład znajduje element, `Test` którego `CommandLine` element podrzędny ma wartość "Examp2.EXE". W przykładzie zastosowano [przykładowy plik XML dokumentu XML: Konfiguracja testu](sample-xml-file-test-configuration.md).

```csharp
XElement root = XElement.Load("TestConfig.xml");
IEnumerable<XElement> tests =
    from el in root.Elements("Test")
    where (string)el.Element("CommandLine") == "Examp2.EXE"
    select el;
foreach (XElement el in tests)
    Console.WriteLine((string)el.Attribute("TestId"));
```

```vb
Dim root As XElement = XElement.Load("TestConfig.xml")
Dim tests As IEnumerable(Of XElement) = _
    From el In root.<Test> _
    Where el.<CommandLine>.Value = "Examp2.EXE" _
    Select el
For Each el as XElement In tests
    Console.WriteLine(el.@TestId)
Next
```

Ten przykład generuje następujące wyniki:

```output
0002
0006
```

Należy zauważyć, że wersja Visual Basic kodu używa [Właściwości osi elementu podrzędnego XML](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [Właściwości osi atrybutu XML](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)i [właściwości wartości XML](../../visual-basic/language-reference/xml-axis/xml-value-property.md).

## <a name="example-find-when-the-xml-is-in-a-namespace"></a>Przykład: Znajdź, kiedy plik XML znajduje się w przestrzeni nazw

Poniższy przykład jest taki sam jak poprzedni, ale dla XML, który znajduje się w przestrzeni nazw. W przykładzie zastosowano [przykładowy plik XML dokumentu XML: Konfiguracja testowa w przestrzeni nazw](sample-xml-file-test-configuration-namespace.md).

Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

```csharp
XElement root = XElement.Load("TestConfigInNamespace.xml");
XNamespace ad = "http://www.adatum.com";
IEnumerable<XElement> tests =
    from el in root.Elements(ad + "Test")
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"
    select el;
foreach (XElement el in tests)
    Console.WriteLine((string)el.Attribute("TestId"));
```

```vb
Imports <xmlns='http://www.adatum.com'>

Module Module1
    Sub Main()
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")
        Dim tests As IEnumerable(Of XElement) = _
            From el In root.<Test> _
            Where el.<CommandLine>.Value = "Examp2.EXE" _
            Select el
        For Each el As XElement In tests
            Console.WriteLine(el.@TestId)
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
0002
0006
```

## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Standardowe operatory zapytań — Omówienie](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Operacje rzutowania](../../csharp/programming-guide/concepts/linq/projection-operations.md)
