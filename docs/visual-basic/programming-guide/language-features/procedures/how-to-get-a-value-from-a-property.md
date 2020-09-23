---
title: 'Porady: pobieranie wartości z właściwości'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 983e2fd22badf4296004404d885df0a07ab2dc74
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071563"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Porady: pobieranie wartości z właściwości (Visual Basic)

Wartość właściwości jest pobierana przez dołączenie nazwy właściwości w wyrażeniu.  
  
 `Get`Procedura właściwości Pobiera wartość, ale nie jest jawnie wywoływana przez nazwę. Właściwość jest używana tak samo jak w przypadku użycia zmiennej. Visual Basic wykonuje wywołania procedur właściwości.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Aby pobrać wartość z właściwości  
  
1. Użyj nazwy właściwości w wyrażeniu tak samo jak w przypadku użycia nazwy zmiennej. Możesz użyć właściwości wszędzie tam, gdzie można użyć zmiennej lub stałej.  
  
     -lub-  
  
     Użyj nazwy właściwości następującego po znaku równości ( `=` ) w instrukcji przypisania.  
  
     Poniższy przykład odczytuje wartość `Now` właściwości Visual Basic, niejawnie wywołując swoją `Get` procedurę.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Jeśli właściwość przyjmuje argumenty, postępuj zgodnie z nazwą właściwości z nawiasami, aby umieścić listę argumentów. Jeśli nie ma żadnych argumentów, możesz opcjonalnie pominąć nawiasy.  
  
3. Umieść argumenty na liście argumentów w nawiasach rozdzielonych przecinkami. Upewnij się, że argumenty są podawane w tej samej kolejności, w której Właściwość definiuje odpowiednie parametry.  
  
 Wartość właściwości uczestniczy w wyrażeniu tak samo jak zmienna lub stała lub jest przechowywana we właściwości lub właściwość po lewej stronie instrukcji przypisania.  
  
## <a name="see-also"></a>Zobacz także

- [Procedury](./index.md)
- [Procedury własności](./property-procedures.md)
- [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)
- [Property — Instrukcja](../../../language-reference/statements/property-statement.md)
- [Różnice pomiędzy właściwościami i zmiennymi w Visual Basic](./differences-between-properties-and-variables.md)
- [Instrukcje: tworzenie właściwości](./how-to-create-a-property.md)
- [Porady: deklarowanie właściwości z mieszanymi poziomami dostępu](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Porady: wywoływanie procedury właściwości](./how-to-call-a-property-procedure.md)
- [Porady: deklarowanie i wywoływanie w właściwości domyślnej w Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Instrukcje: umieszczanie wartości we właściwości](./how-to-put-a-value-in-a-property.md)
