---
title: 'Instrukcje: Przekształcanie fragmentu węzła'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: f5eb8e7826dd132fd46f6f476335416e7dd03269
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722690"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="03c1a-102">Instrukcje: Przekształcanie fragmentu węzła</span><span class="sxs-lookup"><span data-stu-id="03c1a-102">How to: Transform a Node Fragment</span></span>

<span data-ttu-id="03c1a-103">Gdy przekształcasz dane zawarte w <xref:System.Xml.XmlDocument> obiekcie lub <xref:System.Xml.XPath.XPathDocument> , przekształcenia XSLT mają zastosowanie do dokumentu jako całości.</span><span class="sxs-lookup"><span data-stu-id="03c1a-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="03c1a-104">Innymi słowy, jeśli przejdziesz do węzła innego niż węzeł główny dokumentu, nie uniemożliwi to proces przekształcania uzyskuje dostęp do wszystkich węzłów w załadowanym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="03c1a-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="03c1a-105">Aby przekształcić fragment węzła, należy utworzyć oddzielny obiekt zawierający tylko fragment węzła i przekazać ten obiekt do <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="03c1a-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="03c1a-106">Procedury</span><span class="sxs-lookup"><span data-stu-id="03c1a-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="03c1a-107">Aby przekształcić fragment węzła</span><span class="sxs-lookup"><span data-stu-id="03c1a-107">To transform a node fragment</span></span>  
  
1. <span data-ttu-id="03c1a-108">Utwórz obiekt zawierający dokument źródłowy.</span><span class="sxs-lookup"><span data-stu-id="03c1a-108">Create an object containing the source document.</span></span>  
  
2. <span data-ttu-id="03c1a-109">Znajdź fragment węzła, który chcesz przekształcić.</span><span class="sxs-lookup"><span data-stu-id="03c1a-109">Locate the node fragment you wish to transform.</span></span>  
  
3. <span data-ttu-id="03c1a-110">Utwórz oddzielny obiekt za pomocą tylko fragmentu węzła.</span><span class="sxs-lookup"><span data-stu-id="03c1a-110">Create separate object with just the node fragment.</span></span>  
  
4. <span data-ttu-id="03c1a-111">Przekaż fragment węzła do <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="03c1a-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03c1a-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="03c1a-112">Example</span></span>  

 <span data-ttu-id="03c1a-113">Poniższy przykład przekształca fragment węzła i wyświetla wyniki w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="03c1a-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="03c1a-114">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="03c1a-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="03c1a-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="03c1a-115">books.xml</span></span>  

 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="03c1a-116">Single. xsl</span><span class="sxs-lookup"><span data-stu-id="03c1a-116">single.xsl</span></span>  

 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="03c1a-117">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="03c1a-117">Output</span></span>  

 <span data-ttu-id="03c1a-118">Tytuł książki to człowiek z zaufaniem.</span><span class="sxs-lookup"><span data-stu-id="03c1a-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c1a-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="03c1a-119">See also</span></span>

- [<span data-ttu-id="03c1a-120">Używanie klasy XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="03c1a-120">Using the XslCompiledTransform Class</span></span>](using-the-xslcompiledtransform-class.md)
