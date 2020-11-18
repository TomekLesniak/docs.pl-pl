---
title: Usuwanie zawartości węzła z modelu DOM
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: 7b33ebfea244dbe81879c61be3809adcb2a1f5d3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828871"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="b0348-102">Usuwanie zawartości węzła z modelu DOM</span><span class="sxs-lookup"><span data-stu-id="b0348-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="b0348-103">W przypadku typów węzłów, które dziedziczą z <xref:System.Xml.XmlCharacterData> , które są <xref:System.Xml.XmlComment> <xref:System.Xml.XmlText> typami węzłów,, <xref:System.Xml.XmlCDataSection> , <xref:System.Xml.XmlWhitespace> i, można <xref:System.Xml.XmlSignificantWhitespace> usunąć znaki przy użyciu <xref:System.Xml.XmlCharacterData.DeleteData%2A> metody, która usuwa zakres znaków z węzła.</span><span class="sxs-lookup"><span data-stu-id="b0348-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="b0348-104">Jeśli chcesz całkowicie usunąć zawartość, Usuń węzeł, który zawiera zawartość.</span><span class="sxs-lookup"><span data-stu-id="b0348-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="b0348-105">Jeśli chcesz zachować węzeł, ale zawartość jest niepoprawna, zmodyfikuj zawartość.</span><span class="sxs-lookup"><span data-stu-id="b0348-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="b0348-106">Aby uzyskać informacje na temat modyfikowania zawartości węzła, zobacz [Modyfikowanie węzłów, zawartości i wartości w dokumencie XML](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="b0348-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0348-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b0348-107">See also</span></span>

- [<span data-ttu-id="b0348-108">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="b0348-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
