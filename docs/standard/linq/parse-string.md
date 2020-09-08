---
title: Jak analizować ciąg LINQ to XML
description: Można przeanalizować ciąg za pomocą XElement. Parse, aby utworzyć drzewo XML w C# i Visual Basic, i można utworzyć drzewo XML z literałami XML w Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: f4bd22acbf3b11d801c791cc591d882810450fd4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553077"
---
# <a name="how-to-parse-a-string-linq-to-xml"></a><span data-ttu-id="2e3e1-103">Jak przeanalizować ciąg (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="2e3e1-103">How to parse a string (LINQ to XML)</span></span>

<span data-ttu-id="2e3e1-104">W tym artykule pokazano, jak przeanalizować ciąg w celu utworzenia drzewa XML w języku C# i w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-104">This article shows how to parse a string to create an XML tree in C# and in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="2e3e1-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="2e3e1-105">Example</span></span>

<span data-ttu-id="2e3e1-106">Poniższy kod w języku C# pokazuje, jak analizować ciąg XML:</span><span class="sxs-lookup"><span data-stu-id="2e3e1-106">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="2e3e1-107">Można analizować ciąg w Visual Basic w podobny sposób.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-107">You can parse a string in Visual Basic in a similar manner.</span></span> <span data-ttu-id="2e3e1-108">Jest to jednak bardziej wydajne w przypadku używania literałów XML, jak pokazano w poniższym kodzie, ponieważ literały XML nie cierpią od tych samych kar za wydajność, co analizowanie XML z ciągu.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-108">However, it's more efficient to use XML literals, as shown in following code, because XML literals don't suffer from the same performance penalties as parsing XML from a string.</span></span>

<span data-ttu-id="2e3e1-109">Za pomocą literałów XML, można po prostu skopiować i wkleić kod XML do programu Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-109">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>

> [!NOTE]
> <span data-ttu-id="2e3e1-110">Analizowanie tekstu lub ładowanie dokumentu XML z pliku tekstowego jest mniej wydajne niż konstrukcja funkcjonalna.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-110">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="2e3e1-111">Jeśli inicjujesz drzewo XML od kodu, trwa mniej czasu procesora, aby użyć konstrukcji funkcjonalnej niż w celu przeanalizowania tekstu.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-111">If you're initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>

```vb
Dim contacts as XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type="home">206-555-0144</Phone>
            <Phone Type="work">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type="mobile">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>
```

<span data-ttu-id="2e3e1-112">Węzeł główny `Contacts` ma dwa `Contact` węzły.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-112">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="2e3e1-113">Aby uzyskać dostęp do określonych danych w analizowanym formacie XML, należy użyć metody [XElement. elementy ()](xref:System.Xml.Linq.XContainer.Elements) , która w tym przypadku zwraca elementy podrzędne `Contacts` węzła głównego.</span><span class="sxs-lookup"><span data-stu-id="2e3e1-113">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="2e3e1-114">Poniższy przykład drukuje pierwszy `Contact` węzeł konsoli:</span><span class="sxs-lookup"><span data-stu-id="2e3e1-114">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

```vb
Dim contactNodes As List(Of XElement) = contacts.Elements("Contact").ToList()
Console.WriteLine(contactNodes(0))
```

## <a name="see-also"></a><span data-ttu-id="2e3e1-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e3e1-115">See also</span></span>

- [<span data-ttu-id="2e3e1-116">Sposób wyszukiwania elementu o określonym atrybucie</span><span class="sxs-lookup"><span data-stu-id="2e3e1-116">How to find an element with a specific attribute</span></span>](find-element-specific-attribute.md)
