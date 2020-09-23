---
title: 'Porady: używanie klasy definiującej operatory'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 083916a420bf4ad182536363ea46448f6b4c1da5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071355"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Porady: używanie klasy definiującej operatory (Visual Basic)

Jeśli używasz klasy lub struktury, która definiuje własne operatory, możesz uzyskać dostęp do tych operatorów z Visual Basic.  
  
 Definiowanie operatora w klasie lub strukturze jest również nazywane *przeciążeniem* operatora.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład uzyskuje dostęp do struktury SQL <xref:System.Data.SqlTypes.SqlString> , która definiuje operatory konwersji ([Funkcja CType](../../../language-reference/functions/ctype-function.md)) w obu kierunkach między ciągiem SQL i ciągiem Visual Basic. Użyj `CType(` *wyrażenia ciągu SQL*, `String)` Aby przekonwertować ciąg SQL na ciąg Visual Basic i `CType(` *Visual Basic wyrażenie ciągu*, <xref:System.Data.SqlTypes.SqlString> `)` Aby przekonwertować w innym kierunku.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString>Struktura definiuje operator konwersji ([Funkcja CType](../../../language-reference/functions/ctype-function.md)) z elementu `String` do <xref:System.Data.SqlTypes.SqlString> i innego od <xref:System.Data.SqlTypes.SqlString> do `String` . Instrukcja, która przypisuje `title` do `jobTitle` używa pierwszego operatora, a <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> wywołanie funkcji używa drugiego.  
  
## <a name="compile-the-code"></a>Kompiluj kod  

 Upewnij się, że używana Klasa lub struktura definiuje operatora, którego chcesz użyć. Nie należy zakładać, że Klasa lub struktura zdefiniowano każdy operator dostępny do przeciążenia. Aby uzyskać listę dostępnych operatorów, zobacz [instrukcja operatora](../../../language-reference/statements/operator-statement.md).  
  
 Uwzględnij odpowiednią `Imports` instrukcję dla ciągu SQL na początku pliku źródłowego (w tym przypadku <xref:System.Data.SqlTypes> ).  
  
 Projekt musi mieć odwołania do System. Data i System.XML.  
  
## <a name="see-also"></a>Zobacz także

- [Procedury operatorów](./operator-procedures.md)
- [Instrukcje: definiowanie operatora](./how-to-define-an-operator.md)
- [Instrukcje: definiowanie operatora konwersji](./how-to-define-a-conversion-operator.md)
- [Instrukcje: wywoływanie procedury operatora](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Structure — Instrukcja](../../../language-reference/statements/structure-statement.md)
- [Instrukcje: Deklarowanie struktury](../data-types/how-to-declare-a-structure.md)
- [Konwersje jawne i niejawne](../data-types/implicit-and-explicit-conversions.md)
- [Rozszerzanie i zwężanie konwersji](../data-types/widening-and-narrowing-conversions.md)
