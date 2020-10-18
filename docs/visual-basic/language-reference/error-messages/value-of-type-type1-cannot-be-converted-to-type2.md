---
title: Wartości typu „type1” nie można przekonwertować na „type2”.
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 107936aa969690d0cc9fd4a2605cfceea31eeca8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161416"
---
# <a name="bc31194-value-of-type-type1-cannot-be-converted-to-type2"></a>BC31194: nie można przekonwertować wartości typu "type1" na "type2"

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
