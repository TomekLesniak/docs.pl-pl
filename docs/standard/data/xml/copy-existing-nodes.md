---
title: Kopiowanie istniejących węzłów
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: b4ae24f9776456033a876e8ae4d1515d2f669fe0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830951"
---
# <a name="copy-existing-nodes"></a>Kopiowanie istniejących węzłów
Istnieje wiele metod i właściwości w Document Object Model XML (DOM), których można użyć do wybrania węzła, takiego jak **SelectSingleNode**, **ChildNodes [int i]**, **Attributes [int i]**. Po wybraniu węzła można wstawić go do drzewa przy użyciu jednej z metod INSERT, które działają dla danego typu węzła. Jedynym ograniczeniem do wstawiania węzła do drzewa jest to, że dokument nadal musi być poprawnie sformułowany po wstawieniu węzła. Gdy istniejący węzeł zostanie wstawiony do drzewa DOM, zostaje usunięty z jego pierwotnej pozycji i dodany do jego pozycji docelowej.  
  
## <a name="see-also"></a>Zobacz także

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
