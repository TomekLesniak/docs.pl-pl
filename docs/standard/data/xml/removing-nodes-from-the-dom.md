---
title: Usuwanie węzłów z modelu DOM
ms.date: 03/30/2017
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: 5b1a6dfb2da4556e0332441a8e56679aee37a091
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686660"
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="c6580-102">Usuwanie węzłów z modelu DOM</span><span class="sxs-lookup"><span data-stu-id="c6580-102">Removing Nodes from the DOM</span></span>

<span data-ttu-id="c6580-103">Aby usunąć węzeł z Document Object Model XML (DOM), użyj <xref:System.Xml.XmlNode.RemoveChild%2A> metody w celu usunięcia określonego węzła.</span><span class="sxs-lookup"><span data-stu-id="c6580-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="c6580-104">Po usunięciu węzła Metoda usuwa poddrzewo należące do usuwanego węzła; oznacza to, że jeśli nie jest to węzeł liścia.</span><span class="sxs-lookup"><span data-stu-id="c6580-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="c6580-105">Aby usunąć wiele węzłów z modelu DOM, użyj <xref:System.Xml.XmlNode.RemoveAll%2A> metody w celu usunięcia wszystkich elementów podrzędnych i atrybutów, jeśli ma zastosowanie, bieżącego węzła.</span><span class="sxs-lookup"><span data-stu-id="c6580-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="c6580-106">Jeśli pracujesz z programem <xref:System.Xml.XmlNamedNodeMap> , możesz usunąć węzeł przy użyciu <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="c6580-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="c6580-107">Aby usunąć atrybuty, zobacz [usuwanie atrybutów z węzła elementu w modelu dom](removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="c6580-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6580-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c6580-108">See also</span></span>

- [<span data-ttu-id="c6580-109">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="c6580-109">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
