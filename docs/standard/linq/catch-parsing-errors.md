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
# <a name="how-to-catch-parsing-errors-linq-to-xml"></a><span data-ttu-id="142bc-104">Jak przechwytywać błędy analizy (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="142bc-104">How to catch parsing errors (LINQ to XML)</span></span>

<span data-ttu-id="142bc-105">W tym artykule pokazano, jak wykryć źle sformułowany lub nieprawidłowy kod XML w języku C# lub Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="142bc-105">This article shows how to detect badly formed or invalid XML in C# or Visual Basic.</span></span>

<span data-ttu-id="142bc-106">LINQ to XML jest zaimplementowany przy użyciu <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="142bc-106">LINQ to XML is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="142bc-107">Jeśli nieprawidłowo sformułowany lub nieprawidłowy kod XML jest przenoszona do LINQ to XML, <xref:System.Xml.XmlReader> Klasa bazowa zgłosi wyjątek.</span><span class="sxs-lookup"><span data-stu-id="142bc-107">If badly formed or invalid XML is passed to LINQ to XML, the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="142bc-108">Różne metody, które analizują XML, takie jak <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> , nie przechwytują wyjątku; wyjątek może zostać przechwycony przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="142bc-108">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, don't catch the exception; the exception can then be caught by your application.</span></span>

## <a name="example-parse-invalid-xml"></a><span data-ttu-id="142bc-109">Przykład: Przeanalizuj nieprawidłowy kod XML</span><span class="sxs-lookup"><span data-stu-id="142bc-109">Example: Parse invalid XML</span></span>

<span data-ttu-id="142bc-110">Poniższy kod próbuje przeanalizować nieprawidłowego kodu XML.</span><span class="sxs-lookup"><span data-stu-id="142bc-110">The following code tries to parse invalid XML.</span></span>

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

<span data-ttu-id="142bc-111">Ze względu na nieprawidłowy tag końcowy `</Contcts>` , przykład zgłasza następujący wyjątek:</span><span class="sxs-lookup"><span data-stu-id="142bc-111">Because of the invalid end tag `</Contcts>`, the example throws the following exception:</span></span>

```output
The 'Contacts' start tag on line 1 doesn't match the end tag of 'Contcts'. Line 5, position 13.
```

<span data-ttu-id="142bc-112">Informacje o wyjątkach zgłaszanych przez <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> , <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType> , <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> i <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> metodach zawiera <xref:System.Xml.XmlReader> Dokumentacja.</span><span class="sxs-lookup"><span data-stu-id="142bc-112">For information about the exceptions that the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="142bc-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="142bc-113">See also</span></span>

- [<span data-ttu-id="142bc-114">Analizowanie ciągu</span><span class="sxs-lookup"><span data-stu-id="142bc-114">How to parse a string</span></span>](parse-string.md)
