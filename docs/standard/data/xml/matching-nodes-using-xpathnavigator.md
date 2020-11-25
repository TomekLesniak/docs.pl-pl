---
title: Dopasowywanie węzłów przy użyciu klasy XPathNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: 2d598a4ddfe84eec7288d111fc156dd0c555a10e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720129"
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="d1827-102">Dopasowywanie węzłów przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d1827-102">Matching Nodes using XPathNavigator</span></span>

<span data-ttu-id="d1827-103"><xref:System.Xml.XPath.XPathNavigator>Klasa zapewnia metodę, <xref:System.Xml.XPath.XPathNavigator.Matches%2A> Aby określić, czy węzeł dopasowuje wyrażenie XPath.</span><span class="sxs-lookup"><span data-stu-id="d1827-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="d1827-104"><xref:System.Xml.XPath.XPathNavigator.Matches%2A>Metoda przyjmuje wyrażenie XPath jako dane wejściowe i zwraca wartość <xref:System.Boolean> wskazującą, czy bieżący węzeł odpowiada danemu wyrażeniu XPath lub podanemu skompilowanemu <xref:System.Xml.XPath.XPathExpression> obiektowi.</span><span class="sxs-lookup"><span data-stu-id="d1827-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="d1827-105">Zgodne węzły</span><span class="sxs-lookup"><span data-stu-id="d1827-105">Matching Nodes</span></span>  

 <span data-ttu-id="d1827-106"><xref:System.Xml.XPath.XPathNavigator.Matches%2A>Metoda zwraca `true` Jeśli bieżący węzeł pasuje do określonego wyrażenia XPath.</span><span class="sxs-lookup"><span data-stu-id="d1827-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="d1827-107">Na przykład w poniższym przykładzie kodu Metoda zwróci wartość, <xref:System.Xml.XPath.XPathNavigator.Matches%2A> `true` Jeśli bieżącym węzłem jest element `b` , a element `b` ma atrybut `c` .</span><span class="sxs-lookup"><span data-stu-id="d1827-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1827-108"><xref:System.Xml.XPath.XPathNavigator.Matches%2A>Metoda nie zmienia stanu <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="d1827-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1827-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d1827-109">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="d1827-110">Przetwarzanie danych XML przy użyciu modelu danych XPath</span><span class="sxs-lookup"><span data-stu-id="d1827-110">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="d1827-111">Wybieranie danych XML przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d1827-111">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="d1827-112">Obliczanie wyrażeń XPath przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d1827-112">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="d1827-113">Typy węzłów rozpoznawanych w zapytaniach XPath</span><span class="sxs-lookup"><span data-stu-id="d1827-113">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="d1827-114">Zapytania XPath i przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="d1827-114">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="d1827-115">Skompilowane wyrażenia XPath</span><span class="sxs-lookup"><span data-stu-id="d1827-115">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
