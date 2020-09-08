---
title: Jak przechwytywać błędy analizy — LINQ to XML
description: Wyjątek może wystąpić w programie C# lub Visual Basic, jeśli próbuje przeanalizować nieprawidłowy kod XML przy użyciu metody, takiej jak XElement. Parse. Można napisać program, aby przechwycić i odpowiedzieć na takie wyjątki.
ms.date: 7/20/2015
dev_langs:
- csharp
- vb
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: f7679bd5a0726c669eb47ad6ad66e0f64259264b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553023"
---
# <a name="how-to-catch-parsing-errors-linq-to-xml"></a>Jak przechwytywać błędy analizy (LINQ to XML)

W tym artykule pokazano, jak wykryć źle sformułowany lub nieprawidłowy kod XML w języku C# lub Visual Basic.

LINQ to XML jest zaimplementowany przy użyciu <xref:System.Xml.XmlReader> . Jeśli nieprawidłowo sformułowany lub nieprawidłowy kod XML jest przenoszona do LINQ to XML, <xref:System.Xml.XmlReader> Klasa bazowa zgłosi wyjątek. Różne metody, które analizują XML, takie jak <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> , nie przechwytują wyjątku; wyjątek może zostać przechwycony przez aplikację.

## <a name="example-parse-invalid-xml"></a>Przykład: Przeanalizuj nieprawidłowy kod XML

Poniższy kod próbuje przeanalizować nieprawidłowego kodu XML.

```csharp
try {
    XElement contacts = XElement.Parse(
        @"<Contacts>
            <Contact>
                <Name>Jim Wilson</Name>
            </Contact>
          </Contcts>");

    Console.WriteLine(contacts);
}
catch (System.Xml.XmlException e)
{
    Console.WriteLine(e.Message);
}
```

```vb
Try
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _
        "    <Contact>" & vbCrLf & _
        "        <Name>Jim Wilson</Name>" & vbCrLf & _
        "    </Contact>" & vbCrLf & _
        "</Contcts>")

    Console.WriteLine(contacts)
Catch e As System.Xml.XmlException
    Console.WriteLine(e.Message)
End Try
```

Ze względu na nieprawidłowy tag końcowy `</Contcts>` , przykład zgłasza następujący wyjątek:

```output
The 'Contacts' start tag on line 1 doesn't match the end tag of 'Contcts'. Line 5, position 13.
```

Informacje o wyjątkach zgłaszanych przez <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> , <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType> , <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> i <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> metodach zawiera <xref:System.Xml.XmlReader> Dokumentacja.

## <a name="see-also"></a>Zobacz też

- [Analizowanie ciągu](parse-string.md)
