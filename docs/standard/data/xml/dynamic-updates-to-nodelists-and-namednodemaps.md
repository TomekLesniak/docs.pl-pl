---
title: Aktualizacja dynamiczna obiektów NodeLists i NamedNodeMaps
ms.date: 03/30/2017
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 2e23507000a780246c129d470b525f19b8b3b9c9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827662"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="991da-102">Aktualizacja dynamiczna obiektów NodeLists i NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="991da-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="991da-103">Ponieważ **XmlNodeList** i **XmlNamedNodeMap** zawierają zestaw węzłów, a dokument XML jest ładowany do pamięci i jest modyfikowany, organizacja World Wide Web Consortium (W3C) stwierdza, że te obiekty, które zawierają zestawy węzłów, muszą być dynamiczne.</span><span class="sxs-lookup"><span data-stu-id="991da-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="991da-104">Oznacza to, że jeśli dokument źródłowy ulegnie zmianie, dane w tych dwóch obiektach powinny być również zmienione.</span><span class="sxs-lookup"><span data-stu-id="991da-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="991da-105">W związku z tym, jeśli masz element **XmlNodeList** , który zawiera wszystkie elementy podrzędne określonego elementu (na przykład element x), następnie Dodaj dodatkowy element, element Q do dokumentu w obszarze element x. **XmlNodeList** powinien również mieć dodany nowy element Q do swojej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="991da-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="991da-106">Ta sama wartość dotyczy odwrócenia.</span><span class="sxs-lookup"><span data-stu-id="991da-106">The same is true in reverse.</span></span> <span data-ttu-id="991da-107">Jeśli węzeł zostanie dodany do **XmlNodeList**, dokument źródłowy również zostanie zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="991da-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991da-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="991da-108">See also</span></span>

- [<span data-ttu-id="991da-109">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="991da-109">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
