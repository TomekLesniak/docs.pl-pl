---
title: Wartości typu „type1” nie można przekonwertować na „type2”.
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870238"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Wartości typu „type1” nie można przekonwertować na „type2”.

Nie można przekonwertować wartości typu "type1" na "type2". Za pomocą właściwości "value" można uzyskać wartość ciągu pierwszego elementu " \<parentElement> ".  
  
 Podjęto próbę niejawnego rzutowania literału XML na konkretny typ. Literału XML nie można rzutować niejawnie na określony typ.  
  
 **Identyfikator błędu:** BC31194  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Użyj `Value` Właściwości literału XML, aby odwołać się do jej wartości jako `String` . Użyj `CType` funkcji, innej funkcji konwersji typu lub <xref:System.Convert> klasy do rzutowania wartości jako określonego typu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Convert>
- [Funkcje konwersji typu](../functions/type-conversion-functions.md)
- [Literały XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
