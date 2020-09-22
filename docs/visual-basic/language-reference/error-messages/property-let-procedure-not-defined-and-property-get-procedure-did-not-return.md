---
title: Procedura Let właściwości nie została zdefiniowana, a procedura Get właściwości nie zwraca obiektu
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871092"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Procedura Let właściwości nie została zdefiniowana, a procedura Get właściwości nie zwraca obiektu

Niektóre właściwości, metody i operacje mogą dotyczyć tylko `Collection` obiektów. Określono operację lub właściwość, która jest wyłączna dla kolekcji, ale obiekt nie jest kolekcją.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Sprawdź pisownię nazwy obiektu lub właściwości albo sprawdź, czy obiekt jest `Collection` obiektem.  
  
2. Przyjrzyj się `Add` metodzie użytej do dodania obiektu do kolekcji, aby upewnić się, że składnia jest poprawna i że wszystkie identyfikatory zostały wpisane prawidłowo.  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.Collection>
