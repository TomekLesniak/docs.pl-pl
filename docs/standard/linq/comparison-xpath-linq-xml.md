---
title: Porównanie XPath i LINQ to XML LINQ to XML
description: Zapytania XPath i LINQ to XML mogą wykonywać zapytania dotyczące drzew XML. W tych artykułach porównano dwie opcje i znajduje się LINQ to XML zapytań, które mają być w całości, bardziej wydajne, uniwersalne, szybsze, bezpieczniejsze i wygodniejsze.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: b98651ffd7e0df0057164f40bedbc43d654d8c81
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553400"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a><span data-ttu-id="63660-104">Porównanie metody XPath i LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="63660-104">Comparison of XPath and LINQ to XML</span></span>

<span data-ttu-id="63660-105">Wyrażenia XPath i LINQ to XML są podobne na kilka sposobów.</span><span class="sxs-lookup"><span data-stu-id="63660-105">XPath and LINQ to XML are similar in some ways.</span></span> <span data-ttu-id="63660-106">Oba te funkcje mogą służyć do wykonywania zapytań w drzewie XML, zwracając takie wyniki jako kolekcja elementów, Kolekcja atrybutów, kolekcja węzłów lub wartość elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="63660-106">Both can be used to query an XML tree, returning such results as a collection of elements, a collection of attributes, a collection of nodes, or the value of an element or attribute.</span></span> <span data-ttu-id="63660-107">Istnieją jednak znaczące różnice między tymi dwiema opcjami.</span><span class="sxs-lookup"><span data-stu-id="63660-107">However, there are significant differences between the two options.</span></span>

## <a name="differences-between-xpath-and-linq-to-xml"></a><span data-ttu-id="63660-108">Różnice między XPath i LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="63660-108">Differences between XPath and LINQ to XML</span></span>

<span data-ttu-id="63660-109">Wyrażenie XPath nie zezwala na projekcję nowych typów.</span><span class="sxs-lookup"><span data-stu-id="63660-109">XPath doesn't allow projection of new types.</span></span> <span data-ttu-id="63660-110">Można zwrócić kolekcje węzłów tylko z drzewa, podczas gdy LINQ to XML może wykonać zapytanie i projektować obiekt Graph lub drzewo XML w nowym kształcie.</span><span class="sxs-lookup"><span data-stu-id="63660-110">It can only return collections of nodes from the tree, whereas LINQ to XML can execute a query and project an object graph or an XML tree in a new shape.</span></span> <span data-ttu-id="63660-111">Zapytania LINQ to XML mogą wykonywać wiele więcej niż wyrażenia XPath.</span><span class="sxs-lookup"><span data-stu-id="63660-111">LINQ to XML queries can do much more than XPath expressions.</span></span>

<span data-ttu-id="63660-112">Wyrażenia XPath istnieją w izolacji w ciągu.</span><span class="sxs-lookup"><span data-stu-id="63660-112">XPath expressions exist in isolation within a string.</span></span> <span data-ttu-id="63660-113">Kompilator języka C# nie może pomóc w analizie wyrażenia XPath w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="63660-113">The C# compiler can't help parse the XPath expression at compile time.</span></span> <span data-ttu-id="63660-114">Z kolei LINQ to XML zapytania są analizowane i kompilowane przez kompilator języka C#.</span><span class="sxs-lookup"><span data-stu-id="63660-114">By contrast, LINQ to XML queries are parsed and compiled by the C# compiler.</span></span> <span data-ttu-id="63660-115">Kompilator może przechwycić wiele błędów zapytań.</span><span class="sxs-lookup"><span data-stu-id="63660-115">The compiler can catch many query errors.</span></span>

<span data-ttu-id="63660-116">Wyniki XPath nie są jednoznacznie wpisane.</span><span class="sxs-lookup"><span data-stu-id="63660-116">XPath results aren't strongly typed.</span></span> <span data-ttu-id="63660-117">W wielu okolicznościach wynik oceny wyrażenia XPath jest obiektem, a programista może określić właściwy typ i rzutować wynik odpowiednio do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="63660-117">In a number of circumstances, the result of evaluating an XPath expression is an object, and it's up to the developer to determine the proper type and cast the result as necessary.</span></span> <span data-ttu-id="63660-118">Z kolei, projekcje z kwerendy LINQ to XML są jednoznacznie wpisane.</span><span class="sxs-lookup"><span data-stu-id="63660-118">By contrast, the projections from a LINQ to XML query are strongly typed.</span></span>

## <a name="result-ordering"></a><span data-ttu-id="63660-119">Porządkowanie wyników</span><span class="sxs-lookup"><span data-stu-id="63660-119">Result ordering</span></span>

<span data-ttu-id="63660-120">Zalecenie XPath 1,0 stwierdza, że kolekcja będąca wynikiem oceny wyrażenia XPath jest nieuporządkowana.</span><span class="sxs-lookup"><span data-stu-id="63660-120">The XPath 1.0 Recommendation states that a collection that's the result of evaluating an XPath expression is unordered.</span></span>

<span data-ttu-id="63660-121">Jednak podczas iteracji w kolekcji zwróconej przez LINQ to XML metodę osi XPath węzły w kolekcji są zwracane w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="63660-121">However, when iterating through a collection returned by a LINQ to XML XPath axis method, the nodes in the collection are returned in document order.</span></span> <span data-ttu-id="63660-122">Jest to przypadek, nawet w przypadku uzyskiwania dostępu do osi XPath, gdzie predykaty są wyrażane w postaci odwrotnej kolejności dokumentu, takiej jak `preceding` i `preceding-sibling` .</span><span class="sxs-lookup"><span data-stu-id="63660-122">This is the case even when accessing the XPath axes where predicates are expressed in terms of reverse document order, such as `preceding` and `preceding-sibling`.</span></span>

<span data-ttu-id="63660-123">Z kolei większość osi LINQ to XML zwraca kolekcje w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="63660-123">By contrast, most of the LINQ to XML axes return collections in document order.</span></span> <span data-ttu-id="63660-124">Jednak dwie z nich <xref:System.Xml.Linq.XNode.Ancestors%2A> i <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A> , zwracają kolekcje w kolejności wycofywania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="63660-124">However, two of them, <xref:System.Xml.Linq.XNode.Ancestors%2A> and <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, return collections in reverse document order.</span></span> <span data-ttu-id="63660-125">Poniższa tabela zawiera Wyliczenie osi i wskazuje kolejność kolekcji dla każdej z nich:</span><span class="sxs-lookup"><span data-stu-id="63660-125">The following table enumerates the axes, and indicates the collection order for each:</span></span>

|<span data-ttu-id="63660-126">Oś LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="63660-126">LINQ to XML axis</span></span>|<span data-ttu-id="63660-127">Zamawianie</span><span class="sxs-lookup"><span data-stu-id="63660-127">Ordering</span></span>|
|----------------------|--------------|
|<span data-ttu-id="63660-128">XContainer.DescendantNodes</span><span class="sxs-lookup"><span data-stu-id="63660-128">XContainer.DescendantNodes</span></span>|<span data-ttu-id="63660-129">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-129">Document order</span></span>|
|<span data-ttu-id="63660-130">XContainer. Descendants</span><span class="sxs-lookup"><span data-stu-id="63660-130">XContainer.Descendants</span></span>|<span data-ttu-id="63660-131">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-131">Document order</span></span>|
|<span data-ttu-id="63660-132">XContainer. elementy</span><span class="sxs-lookup"><span data-stu-id="63660-132">XContainer.Elements</span></span>|<span data-ttu-id="63660-133">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-133">Document order</span></span>|
|<span data-ttu-id="63660-134">XContainer. węzły</span><span class="sxs-lookup"><span data-stu-id="63660-134">XContainer.Nodes</span></span>|<span data-ttu-id="63660-135">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-135">Document order</span></span>|
|<span data-ttu-id="63660-136">XContainer.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="63660-136">XContainer.NodesAfterSelf</span></span>|<span data-ttu-id="63660-137">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-137">Document order</span></span>|
|<span data-ttu-id="63660-138">XContainer.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="63660-138">XContainer.NodesBeforeSelf</span></span>|<span data-ttu-id="63660-139">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-139">Document order</span></span>|
|<span data-ttu-id="63660-140">XElement. AncestorsAndSelf</span><span class="sxs-lookup"><span data-stu-id="63660-140">XElement.AncestorsAndSelf</span></span>|<span data-ttu-id="63660-141">Zamówienie odwrócenia dokumentu</span><span class="sxs-lookup"><span data-stu-id="63660-141">Reverse document order</span></span>|
|<span data-ttu-id="63660-142">XElement. Attributes</span><span class="sxs-lookup"><span data-stu-id="63660-142">XElement.Attributes</span></span>|<span data-ttu-id="63660-143">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-143">Document order</span></span>|
|<span data-ttu-id="63660-144">XElement. DescendantNodesAndSelf</span><span class="sxs-lookup"><span data-stu-id="63660-144">XElement.DescendantNodesAndSelf</span></span>|<span data-ttu-id="63660-145">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-145">Document order</span></span>|
|<span data-ttu-id="63660-146">XElement. DescendantsAndSelf</span><span class="sxs-lookup"><span data-stu-id="63660-146">XElement.DescendantsAndSelf</span></span>|<span data-ttu-id="63660-147">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-147">Document order</span></span>|
|<span data-ttu-id="63660-148">XNode. przodków</span><span class="sxs-lookup"><span data-stu-id="63660-148">XNode.Ancestors</span></span>|<span data-ttu-id="63660-149">Zamówienie odwrócenia dokumentu</span><span class="sxs-lookup"><span data-stu-id="63660-149">Reverse document order</span></span>|
|<span data-ttu-id="63660-150">XNode.ElementsAfterSelf</span><span class="sxs-lookup"><span data-stu-id="63660-150">XNode.ElementsAfterSelf</span></span>|<span data-ttu-id="63660-151">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-151">Document order</span></span>|
|<span data-ttu-id="63660-152">XNode.ElementsBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="63660-152">XNode.ElementsBeforeSelf</span></span>|<span data-ttu-id="63660-153">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-153">Document order</span></span>|
|<span data-ttu-id="63660-154">XNode.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="63660-154">XNode.NodesAfterSelf</span></span>|<span data-ttu-id="63660-155">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-155">Document order</span></span>|
|<span data-ttu-id="63660-156">XNode.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="63660-156">XNode.NodesBeforeSelf</span></span>|<span data-ttu-id="63660-157">Kolejność dokumentów</span><span class="sxs-lookup"><span data-stu-id="63660-157">Document order</span></span>|

## <a name="positional-predicates"></a><span data-ttu-id="63660-158">Predykaty pozycyjne</span><span class="sxs-lookup"><span data-stu-id="63660-158">Positional predicates</span></span>

<span data-ttu-id="63660-159">W wyrażeniu XPath predykaty pozycyjne są wyrażane w zakresie kolejności dokumentu dla wielu osi, ale są wyrażane w kolejności odwrotnego dokumentu dla odwróconych osi.</span><span class="sxs-lookup"><span data-stu-id="63660-159">Within an XPath expression, positional predicates are expressed in terms of document order for many axes, but are expressed in reverse document order for reverse axes.</span></span> <span data-ttu-id="63660-160">Odwrotne osie to: `preceding` , `preceding-sibling` , `ancestor` , i `ancestor-or-self` .</span><span class="sxs-lookup"><span data-stu-id="63660-160">The reverse axes are: `preceding`, `preceding-sibling`, `ancestor`, and `ancestor-or-self`.</span></span> <span data-ttu-id="63660-161">Na przykład wyrażenie XPath `preceding-sibling::*[1]` zwraca bezpośrednio poprzedni element równorzędny.</span><span class="sxs-lookup"><span data-stu-id="63660-161">For example, the XPath expression `preceding-sibling::*[1]` returns the immediately preceding sibling.</span></span> <span data-ttu-id="63660-162">Dzieje się tak, mimo że końcowy zestaw wyników jest przedstawiony w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="63660-162">This is the case even though the final result set is presented in document order.</span></span>

<span data-ttu-id="63660-163">Z kolei wszystkie predykaty pozycyjne w LINQ to XML są zawsze wyrażane w warunkach kolejności osi.</span><span class="sxs-lookup"><span data-stu-id="63660-163">By contrast, all positional predicates in LINQ to XML are always expressed in terms of the order of the axis.</span></span> <span data-ttu-id="63660-164">Na przykład `anElement.ElementsBeforeSelf().ElementAt(0)` zwraca pierwszy element podrzędny obiektu nadrzędnego z zapytania elementu, a nie bezpośrednio poprzedzającego element równorzędny.</span><span class="sxs-lookup"><span data-stu-id="63660-164">For example, `anElement.ElementsBeforeSelf().ElementAt(0)` returns the first child element of the parent of the queried element, not the immediate preceding sibling.</span></span> <span data-ttu-id="63660-165">Inny przykład: `anElement.Ancestors().ElementAt(0)` zwraca element nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="63660-165">Another example: `anElement.Ancestors().ElementAt(0)` returns the parent element.</span></span>

<span data-ttu-id="63660-166">Aby znaleźć bezpośrednio poprzedzający element w LINQ to XML, należy napisać następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="63660-166">If you wanted to find the immediately preceding element in LINQ to XML, you would write the following expression:</span></span>

```csharp
ElementsBeforeSelf().Last()
```

```vb
ElementsBeforeSelf().Last()
```

## <a name="performance-differences"></a><span data-ttu-id="63660-167">Różnice w wydajności</span><span class="sxs-lookup"><span data-stu-id="63660-167">Performance differences</span></span>

<span data-ttu-id="63660-168">Zapytania XPath korzystające z funkcji XPath w LINQ to XML będą wolniejsze niż LINQ to XML zapytań.</span><span class="sxs-lookup"><span data-stu-id="63660-168">XPath queries that use the XPath functionality in LINQ to XML will be slower than LINQ to XML queries.</span></span>

## <a name="comparison-of-composition"></a><span data-ttu-id="63660-169">Porównanie kompozycji</span><span class="sxs-lookup"><span data-stu-id="63660-169">Comparison of composition</span></span>

<span data-ttu-id="63660-170">Kompozycja LINQ to XML zapytania jest podobna do składowej wyrażenia XPath, ale składnia jest bardzo inna.</span><span class="sxs-lookup"><span data-stu-id="63660-170">Composition of a LINQ to XML query is similar to composition of an XPath expression, but the syntax is very different.</span></span>

<span data-ttu-id="63660-171">Na przykład jeśli masz element w zmiennej o nazwie `customers` i chcesz znaleźć element grandchild o nazwie `CompanyName` pod wszystkimi elementami podrzędnymi o nazwie `Customer` , napisz wyrażenie XPath:</span><span class="sxs-lookup"><span data-stu-id="63660-171">For example, if you have an element in a variable named `customers`, and you want to find a grandchild element named `CompanyName` under all child elements named `Customer`, you would write this XPath expression:</span></span>

```csharp
customers.XPathSelectElements("./Customer/CompanyName")
```

```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

<span data-ttu-id="63660-172">Odpowiednik kwerendy LINQ to XML jest:</span><span class="sxs-lookup"><span data-stu-id="63660-172">The equivalent LINQ to XML query is:</span></span>

```csharp
customers.Elements("Customer").Elements("CompanyName")
```

```vb
customers.Elements("Customer").Elements("CompanyName")
```

<span data-ttu-id="63660-173">Istnieją podobne równoległości dla każdej z osi XPath.</span><span class="sxs-lookup"><span data-stu-id="63660-173">There are similar parallels for each of the XPath axes.</span></span>

|<span data-ttu-id="63660-174">Oś XPath</span><span class="sxs-lookup"><span data-stu-id="63660-174">XPath axis</span></span>|<span data-ttu-id="63660-175">Oś LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="63660-175">LINQ to XML axis</span></span>|
|----------------|----------------------|
|<span data-ttu-id="63660-176">element podrzędny (oś domyślna)</span><span class="sxs-lookup"><span data-stu-id="63660-176">child (the default axis)</span></span>|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-177">Nadrzędne (..)</span><span class="sxs-lookup"><span data-stu-id="63660-177">Parent (..)</span></span>|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-178">oś atrybutów (@)</span><span class="sxs-lookup"><span data-stu-id="63660-178">attribute axis (@)</span></span>|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="63660-179">lub</span><span class="sxs-lookup"><span data-stu-id="63660-179">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-180">oś nadrzędna</span><span class="sxs-lookup"><span data-stu-id="63660-180">ancestor axis</span></span>|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-181">obiekt nadrzędny lub samosamej osi</span><span class="sxs-lookup"><span data-stu-id="63660-181">ancestor-or-self axis</span></span>|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-182">oś elementu podrzędnego (//)</span><span class="sxs-lookup"><span data-stu-id="63660-182">descendant axis (//)</span></span>|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="63660-183">lub</span><span class="sxs-lookup"><span data-stu-id="63660-183">or</span></span><br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-184">elementy podrzędne lub samodzielne</span><span class="sxs-lookup"><span data-stu-id="63660-184">descendant-or-self</span></span>|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="63660-185">lub</span><span class="sxs-lookup"><span data-stu-id="63660-185">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-186">poniżej — element równorzędny</span><span class="sxs-lookup"><span data-stu-id="63660-186">following-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="63660-187">lub</span><span class="sxs-lookup"><span data-stu-id="63660-187">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-188">Poprzedni element równorzędny</span><span class="sxs-lookup"><span data-stu-id="63660-188">preceding-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="63660-189">lub</span><span class="sxs-lookup"><span data-stu-id="63660-189">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|
|<span data-ttu-id="63660-190">dodaje</span><span class="sxs-lookup"><span data-stu-id="63660-190">following</span></span>|<span data-ttu-id="63660-191">Brak bezpośredniego odpowiednika.</span><span class="sxs-lookup"><span data-stu-id="63660-191">No direct equivalent.</span></span>|
|<span data-ttu-id="63660-192">licencyjn</span><span class="sxs-lookup"><span data-stu-id="63660-192">preceding</span></span>|<span data-ttu-id="63660-193">Brak bezpośredniego odpowiednika.</span><span class="sxs-lookup"><span data-stu-id="63660-193">No direct equivalent.</span></span>|
