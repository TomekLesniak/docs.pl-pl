---
title: Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna — LINQ to XML
description: Zobacz przykłady dwóch różnych metod modyfikowania drzew XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b5afc31d-a325-4ec6-bf17-0ff90a20ffca
ms.openlocfilehash: 71f76d12024bb07cf90df2299df14646ae271b47
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552972"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml"></a><span data-ttu-id="ce06e-103">Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ce06e-103">In-memory XML tree modification vs. functional construction (LINQ to XML)</span></span>

<span data-ttu-id="ce06e-104">Modyfikowanie drzewa XML jest tradycyjnym podejściem do zmiany kształtu dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="ce06e-104">Modifying an XML tree in place is a traditional approach to changing the shape of an XML document.</span></span> <span data-ttu-id="ce06e-105">Typowa aplikacja ładuje dokument do magazynu danych, takiego jak DOM lub LINQ to XML; używa interfejsu programowania do wstawiania lub usuwania węzłów lub zmiany ich zawartości; a następnie zapisuje plik XML do pliku lub przesyła go za pośrednictwem sieci.</span><span class="sxs-lookup"><span data-stu-id="ce06e-105">A typical application loads a document into a data store such as DOM or LINQ to XML; uses a programming interface to insert or delete nodes, or change their content; and then saves the XML to a file or transmits it over a network.</span></span>

<span data-ttu-id="ce06e-106">LINQ to XML zapewnia kolejną metodę, która jest przydatna w wielu scenariuszach: *konstrukcja funkcjonalna*.</span><span class="sxs-lookup"><span data-stu-id="ce06e-106">LINQ to XML enables another approach that is useful in many scenarios: *functional construction*.</span></span> <span data-ttu-id="ce06e-107">Konstrukcja funkcjonalna traktuje modyfikowanie danych jako problem transformacji, a nie jako szczegółowe manipulowanie magazynem danych.</span><span class="sxs-lookup"><span data-stu-id="ce06e-107">Functional construction treats modifying data as a problem of transformation, rather than as detailed manipulation of a data store.</span></span> <span data-ttu-id="ce06e-108">Jeśli możesz wykonać reprezentację danych i Przekształć ją efektywnie z jednego formularza na inny, wynik jest taki sam jak w przypadku, gdy został przestawiony jeden magazyn danych i manipulowanie nim w jakiś sposób, aby zastosować inny kształt.</span><span class="sxs-lookup"><span data-stu-id="ce06e-108">If you can take a representation of data and transform it efficiently from one form to another, the result is the same as if you took one data store and manipulated it in some way to take another shape.</span></span> <span data-ttu-id="ce06e-109">Najważniejszym podejściem do konstrukcji funkcjonalnej jest przekazanie wyników zapytań do <xref:System.Xml.Linq.XDocument> i <xref:System.Xml.Linq.XElement> konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="ce06e-109">A key to the functional construction approach is to pass the results of queries to <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> constructors.</span></span>

<span data-ttu-id="ce06e-110">W wielu przypadkach można napisać przekształcenie kod w ułamku czasu, jaki mógłby wykonać w celu manipulowania magazynem danych, a otrzymany kod jest bardziej niezawodny i łatwiejszy w obsłudze.</span><span class="sxs-lookup"><span data-stu-id="ce06e-110">In many cases you can write the transformational code in a fraction of the time that it would take to manipulate the data store, and the resulting code is more robust and easier to maintain.</span></span> <span data-ttu-id="ce06e-111">W takich przypadkach, mimo że podejście przekształcenie może mieć większą moc obliczeniową, jest to bardziej efektywny sposób modyfikacji danych.</span><span class="sxs-lookup"><span data-stu-id="ce06e-111">In these cases, even though the transformational approach can take more processing power, it's a more effective way to modify data.</span></span> <span data-ttu-id="ce06e-112">Jeśli programista zna podejście funkcjonalne, kod wynikający z wielu przypadków jest łatwiejszy do zrozumienia i można łatwo znaleźć kod, który modyfikuje każdą część drzewa.</span><span class="sxs-lookup"><span data-stu-id="ce06e-112">If a developer is familiar with the functional approach, the resulting code in many cases is easier to understand, and it's easy to find the code that modifies each part of the tree.</span></span>

<span data-ttu-id="ce06e-113">Podejście, gdzie modyfikujesz drzewo XML, jest bardziej znane dla wielu programistów modelu DOM, natomiast kod zapisany przy użyciu podejścia funkcjonalnego może wyglądać nieznajomo dla deweloperów, który nie rozumie tego podejścia.</span><span class="sxs-lookup"><span data-stu-id="ce06e-113">The approach where you modify an XML tree in place is more familiar to many DOM programmers, whereas code written using the functional approach might look unfamiliar to a developer who doesn't yet understand that approach.</span></span> <span data-ttu-id="ce06e-114">Jeśli konieczne jest tylko małe modyfikacje w dużym drzewie XML, podejście, w którym można modyfikować drzewo w wielu przypadkach, zajmie mniej czasu procesora.</span><span class="sxs-lookup"><span data-stu-id="ce06e-114">If you have to only make a small modification to a large XML tree, the approach where you modify a tree in place in many cases will take less CPU time.</span></span>

<span data-ttu-id="ce06e-115">W tym artykule przedstawiono przykłady obu tych metod.</span><span class="sxs-lookup"><span data-stu-id="ce06e-115">This article provides examples of both approaches.</span></span> <span data-ttu-id="ce06e-116">Załóżmy, że chcesz zmodyfikować następujący prosty dokument XML, aby atrybuty staną się elementami:</span><span class="sxs-lookup"><span data-stu-id="ce06e-116">Suppose you want to modify the following simple XML document so that the attributes become elements:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Root Data1="123" Data2="456">
  <Child1>Content</Child1>
</Root>
```

<span data-ttu-id="ce06e-117">Pierwszy z poniższych przykładów używa tradycyjnego podejścia do modyfikacji w miejscu, a drugi używa podejścia konstruowania funkcjonalnego.</span><span class="sxs-lookup"><span data-stu-id="ce06e-117">The first of the following examples uses the traditional in-place modification approach, and the second uses the functional construction approach.</span></span>

## <a name="example-transform-attributes-into-elements-with-the-traditional-in-place-approach"></a><span data-ttu-id="ce06e-118">Przykład: Przekształć atrybuty na elementy z tradycyjnym podejściem w miejscu</span><span class="sxs-lookup"><span data-stu-id="ce06e-118">Example: Transform attributes into elements with the traditional in-place approach</span></span>

<span data-ttu-id="ce06e-119">Można napisać kod proceduralny, aby utworzyć elementy z atrybutów, a następnie usunąć atrybuty w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="ce06e-119">You can write some procedural code to create elements from the attributes, and then delete the attributes, as follows:</span></span>

```csharp
XElement root = XElement.Load("Data.xml");
foreach (XAttribute att in root.Attributes()) {
    root.Add(new XElement(att.Name, (string)att));
}
root.Attributes().Remove();
Console.WriteLine(root);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
For Each att As XAttribute In root.Attributes()
    root.Add(New XElement(att.Name, att.Value))
Next
root.Attributes().Remove()
Console.WriteLine(root)
```

<span data-ttu-id="ce06e-120">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="ce06e-120">This example produces the following output:</span></span>

```xml
<Root>
  <Child1>Content</Child1>
  <Data1>123</Data1>
  <Data2>456</Data2>
</Root>
```

## <a name="example-transform-attributes-into-elements-with-the-functional-construction-approach"></a><span data-ttu-id="ce06e-121">Przykład: Przekształć atrybuty na elementy z podejściem konstrukcja funkcjonalna</span><span class="sxs-lookup"><span data-stu-id="ce06e-121">Example: Transform attributes into elements with the functional construction approach</span></span>

<span data-ttu-id="ce06e-122">Z kolei podejście funkcjonalne obejmuje kod służący do tworzenia nowego drzewa, wybierania i wybierania elementów i atrybutów z drzewa źródłowego i przekształcania ich zgodnie z potrzebami, gdy są dodawane do nowego drzewa.</span><span class="sxs-lookup"><span data-stu-id="ce06e-122">By contrast, a functional approach consists of code to form a new tree, picking and choosing elements and attributes from the source tree, and transforming them as appropriate as they're added to the new tree.</span></span>

```csharp
XElement root = XElement.Load("Data.xml");
XElement newTree = new XElement("Root",
    root.Element("Child1"),
    from att in root.Attributes()
    select new XElement(att.Name, (string)att)
);
Console.WriteLine(newTree);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
Dim newTree As XElement = _
    <Root>
        <%= root.<Child1> %>
        <%= From att In root.Attributes() _
            Select New XElement(att.Name, att.Value) %>
    </Root>
Console.WriteLine(newTree)
```

<span data-ttu-id="ce06e-123">Ten przykład wyprowadza ten sam kod XML jako pierwszy przykład.</span><span class="sxs-lookup"><span data-stu-id="ce06e-123">This example outputs the same XML as the first example.</span></span> <span data-ttu-id="ce06e-124">Należy jednak zauważyć, że w metodzie funkcjonalnej można zobaczyć uzyskaną strukturę nowego kodu XML.</span><span class="sxs-lookup"><span data-stu-id="ce06e-124">However, notice that you can actually see the resulting structure of the new XML in the functional approach.</span></span> <span data-ttu-id="ce06e-125">Można zobaczyć `Root` , jak utworzyć element, kod, który ściąga `Child1` element z drzewa źródłowego, oraz kod, który przekształca atrybuty z drzewa źródłowego do elementów w nowym drzewie.</span><span class="sxs-lookup"><span data-stu-id="ce06e-125">You can see the creation of the `Root` element, the code that pulls the `Child1` element from the source tree, and the code that transforms the attributes from the source tree to elements in the new tree.</span></span>

<span data-ttu-id="ce06e-126">Przykład funkcjonalny w tym przypadku nie jest krótszy ani łatwiejszy od pierwszego przykładu.</span><span class="sxs-lookup"><span data-stu-id="ce06e-126">The functional example in this case is neither shorter nor simpler than the first example.</span></span> <span data-ttu-id="ce06e-127">Jeśli jednak w drzewie XML wprowadzono wiele zmian, podejście proceduralne staje się dość skomplikowane i dość obtuse.</span><span class="sxs-lookup"><span data-stu-id="ce06e-127">However, if you have many changes to make to an XML tree, the procedural approach will become quite complex and somewhat obtuse.</span></span> <span data-ttu-id="ce06e-128">Natomiast w przypadku korzystania z podejścia funkcjonalnego nadal wystarczy utworzyć żądany kod XML, a następnie osadzić zapytania i wyrażenia, aby ściągnąć odpowiednią zawartość.</span><span class="sxs-lookup"><span data-stu-id="ce06e-128">In contrast, when using the functional approach, you still just form the desired XML, embedding queries and expressions as appropriate, to pull in the desired content.</span></span> <span data-ttu-id="ce06e-129">Podejście funkcjonalne daje kod, który jest łatwiejszy w obsłudze.</span><span class="sxs-lookup"><span data-stu-id="ce06e-129">The functional approach yields code that is easier to maintain.</span></span>

<span data-ttu-id="ce06e-130">Należy zauważyć, że w tym przypadku podejście funkcjonalne prawdopodobnie nie będzie działać w sposób niewidoczny, a także podejście do manipulowania drzewem.</span><span class="sxs-lookup"><span data-stu-id="ce06e-130">Notice that in this case the functional approach probably would not perform quite as well as the tree manipulation approach.</span></span> <span data-ttu-id="ce06e-131">Główny problem polega na tym, że podejście funkcjonalne tworzy więcej obiektów krótkich.</span><span class="sxs-lookup"><span data-stu-id="ce06e-131">The main issue is that the functional approach creates more short-lived objects.</span></span> <span data-ttu-id="ce06e-132">Jednak kompromis jest skuteczny, jeśli użycie podejścia funkcjonalnego pozwala zwiększyć produktywność programistyczną.</span><span class="sxs-lookup"><span data-stu-id="ce06e-132">However, the tradeoff is an effective one if using the functional approach allows for greater programmer productivity.</span></span>

<span data-ttu-id="ce06e-133">Jest to bardzo prosty przykład, ale służy do wyświetlania różnicy między dwoma podejściami.</span><span class="sxs-lookup"><span data-stu-id="ce06e-133">This is a very simple example, but it serves to show the difference in philosophy between the two approaches.</span></span> <span data-ttu-id="ce06e-134">Podejście funkcjonalne daje większe korzyści produktywności związane z transformą większych dokumentów XML.</span><span class="sxs-lookup"><span data-stu-id="ce06e-134">The functional approach yields greater productivity gains for transforming larger XML documents.</span></span>
