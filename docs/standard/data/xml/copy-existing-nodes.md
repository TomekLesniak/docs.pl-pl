---
title: Kopiowanie istniejących węzłów
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: 651e9fc9dc0d1a50a2d15d382b3ca65f7fd4b7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701435"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="b64dd-102">Kopiowanie istniejących węzłów</span><span class="sxs-lookup"><span data-stu-id="b64dd-102">Copy Existing Nodes</span></span>

<span data-ttu-id="b64dd-103">Istnieje wiele metod i właściwości w Document Object Model XML (DOM), których można użyć do wybrania węzła, takiego jak **SelectSingleNode**, **ChildNodes [int i]**, **Attributes [int i]**.</span><span class="sxs-lookup"><span data-stu-id="b64dd-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="b64dd-104">Po wybraniu węzła można wstawić go do drzewa przy użyciu jednej z metod INSERT, które działają dla danego typu węzła.</span><span class="sxs-lookup"><span data-stu-id="b64dd-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="b64dd-105">Jedynym ograniczeniem do wstawiania węzła do drzewa jest to, że dokument nadal musi być poprawnie sformułowany po wstawieniu węzła.</span><span class="sxs-lookup"><span data-stu-id="b64dd-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="b64dd-106">Gdy istniejący węzeł zostanie wstawiony do drzewa DOM, zostaje usunięty z jego pierwotnej pozycji i dodany do jego pozycji docelowej.</span><span class="sxs-lookup"><span data-stu-id="b64dd-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64dd-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b64dd-107">See also</span></span>

- [<span data-ttu-id="b64dd-108">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="b64dd-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
