---
title: Jak pobrać skróconą wartość elementu LINQ to XML
description: Użyj `ShallowValue` metody rozszerzającej, aby pobrać płytki wartość elementu. Skrócona wartość jest wartością tego elementu. oznacza to, że nie zawiera wartości elementów podrzędnych.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 761ffc07b13ebdc652b75bf96ba5b121c7912fd7
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553663"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-linq-to-xml"></a>Jak pobrać skróconą wartość elementu (LINQ to XML)

W tym artykule pokazano, jak pobrać skróconą wartość elementu, który jest wartością tylko tego elementu, bez uwzględniania wartości elementów potomnych. Pobieranie skróconej wartości jest przydatne, gdy chcesz wybrać elementy na podstawie ich zawartości.

W przypadku użycia rzutowania lub <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości do pobrania wartości elementu, wartość zawiera elementy podrzędne. Aby pobrać skróconą wartość, można użyć `ShallowValue` metody rozszerzenia, jak pokazano w poniższym przykładzie. Przykład deklaruje metodę rozszerzenia, która pobiera płytki wartość elementu. Następnie używa metody rozszerzającej w zapytaniu, aby wyświetlić listę wszystkich elementów, które zawierają obliczoną wartość.

## <a name="example-use-the-shallowvalue-extension-method-to-retrieve-the-shallow-value-of-an-element"></a>Przykład: Użyj `ShallowValue` metody rozszerzającej, aby pobrać płytki wartość elementu

W przykładach jest użyty plik tekstowy Report.xml, który zawiera następujące elementy:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Report>
  <Section>
    <Heading>
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>
      <Column Name="Name">=Customer.Name.Heading</Column>
    </Heading>
    <Detail>
      <Column Name="CustomerId">=Customer.CustomerId</Column>
      <Column Name="Name">=Customer.Name</Column>
    </Detail>
  </Section>
</Report>
```

Oto kod dla przykładu:

```csharp
public static class MyExtensions
{
    public static string ShallowValue(this XElement xe)
    {
        return xe
               .Nodes()
               .OfType<XText>()
               .Aggregate(new StringBuilder(),
                          (s, c) => s.Append(c),
                          s => s.ToString());
    }
}

class Program
{
    static void Main(string[] args)
    {
        XElement root = XElement.Load("Report.xml");

        IEnumerable<XElement> query = from el in root.Descendants()
                                      where el.ShallowValue().StartsWith("=")
                                      select el;

        foreach (var q in query)
        {
            Console.WriteLine("{0}{1}{2}",
                q.Name.ToString().PadRight(8),
                q.Attribute("Name").ToString().PadRight(20),
                q.ShallowValue());
        }
    }
}
```

```vb
Module Module1
    <System.Runtime.CompilerServices.Extension()> _
    Public Function ShallowValue(ByVal xe As XElement)
        Return xe _
               .Nodes() _
               .OfType(Of XText)() _
               .Aggregate(New StringBuilder(), _
                              Function(s, c) s.Append(c), _
                              Function(s) s.ToString())
    End Function

    Sub Main()
        Dim root As XElement = XElement.Load("Report.xml")

        Dim query As IEnumerable(Of XElement) = _
            From el In root.Descendants() _
            Where (el.ShallowValue().StartsWith("=")) _
            Select el

        For Each q As XElement In query
            Console.WriteLine("{0}{1}{2}", _
                q.Name.ToString().PadRight(8), _
                q.Attribute("Name").ToString().PadRight(20), _
                q.ShallowValue())
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
Column  Name="CustomerId"   =Customer.CustomerId.Heading
Column  Name="Name"         =Customer.Name.Heading
Column  Name="CustomerId"   =Customer.CustomerId
Column  Name="Name"         =Customer.Name
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
