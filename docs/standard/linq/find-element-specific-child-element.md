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
# <a name="how-to-find-an-element-with-a-specific-child-element-linq-to-xml"></a><span data-ttu-id="58944-103">Jak znaleźć element z określonym elementem podrzędnym (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="58944-103">How to find an element with a specific child element (LINQ to XML)</span></span>

<span data-ttu-id="58944-104">W tym artykule pokazano, jak znaleźć element, którego element podrzędny ma określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="58944-104">This article shows how to find an element whose child element has a specific value.</span></span>

## <a name="example-find-an-element-whose-child-element-has-a-specific-value"></a><span data-ttu-id="58944-105">Przykład: Znajdź element, którego element podrzędny ma określoną wartość</span><span class="sxs-lookup"><span data-stu-id="58944-105">Example: Find an element whose child element has a specific value</span></span>

<span data-ttu-id="58944-106">Przykład znajduje element, `Test` którego `CommandLine` element podrzędny ma wartość "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="58944-106">The example finds the `Test` element whose `CommandLine` child element has a value of "Examp2.EXE".</span></span> <span data-ttu-id="58944-107">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: Konfiguracja testu](sample-xml-file-test-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="58944-107">The example uses XML document [Sample XML file: Test configuration](sample-xml-file-test-configuration.md).</span></span>

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

<span data-ttu-id="58944-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="58944-108">This example produces the following output:</span></span>

```output
0002
0006
```

<span data-ttu-id="58944-109">Należy zauważyć, że wersja Visual Basic kodu używa [Właściwości osi elementu podrzędnego XML](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [Właściwości osi atrybutu XML](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)i [właściwości wartości XML](../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="58944-109">Note that the Visual Basic version of the code uses the [XML Child axis property](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

## <a name="example-find-when-the-xml-is-in-a-namespace"></a><span data-ttu-id="58944-110">Przykład: Znajdź, kiedy plik XML znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="58944-110">Example: Find when the XML is in a namespace</span></span>

<span data-ttu-id="58944-111">Poniższy przykład jest taki sam jak poprzedni, ale dla XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="58944-111">The following example does the same as the previous one, but for XML that's in a namespace.</span></span> <span data-ttu-id="58944-112">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: Konfiguracja testowa w przestrzeni nazw](sample-xml-file-test-configuration-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="58944-112">The example uses XML document [Sample XML file: Test configuration in a namespace](sample-xml-file-test-configuration-namespace.md).</span></span>

<span data-ttu-id="58944-113">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="58944-113">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

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

<span data-ttu-id="58944-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="58944-114">This example produces the following output:</span></span>

```output
0002
0006
```

## <a name="see-also"></a><span data-ttu-id="58944-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="58944-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="58944-116">Standardowe operatory zapytań — Omówienie</span><span class="sxs-lookup"><span data-stu-id="58944-116">Standard Query Operators Overview</span></span>](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="58944-117">Operacje rzutowania</span><span class="sxs-lookup"><span data-stu-id="58944-117">Projection Operations</span></span>](../../csharp/programming-guide/concepts/linq/projection-operations.md)
