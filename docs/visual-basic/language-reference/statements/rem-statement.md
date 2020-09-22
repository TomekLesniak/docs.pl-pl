---
title: REM, instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 6161a9f7e589988882b5f76477bc069afd2b9b41
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871953"
---
# <a name="rem-statement-visual-basic"></a>REM — Instrukcja (Visual Basic)

Służy do uwzględnienia uwag objaśniających kod źródłowy programu.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Części  

 `comment`  
 Opcjonalny. Tekst komentarza, który ma zostać uwzględniony. Między `REM` słowem kluczowym i `comment` .  
  
## <a name="remarks"></a>Uwagi  

 Instrukcję można umieścić `REM` samodzielnie w wierszu lub można ją umieścić w wierszu po innej instrukcji. `REM`Instrukcja musi być ostatnią instrukcją w wierszu. Jeśli jest ona zgodna z inną instrukcją, `REM` musi być oddzielona od tej instrukcji spacją.  
  
 Można użyć pojedynczego cudzysłowu ( `'` ) zamiast `REM` . Dzieje się tak, gdy komentarz jest podążany za inną instrukcją w tym samym wierszu lub w wierszu.  
  
> [!NOTE]
> Nie można kontynuować `REM` instrukcji przy użyciu sekwencji kontynuacji wiersza ( `_` ). Po rozpoczęciu komentarza kompilator nie bada znaków pod kątem specjalnego znaczenia. W przypadku komentarza z wieloma wierszami Użyj innej `REM` instrukcji lub symbolu komentarza ( `'` ) w każdym wierszu.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład ilustruje `REM` instrukcję, która jest używana do dołączania uwag objaśniających do programu. Pokazuje również alternatywę użycia znaku pojedynczego cudzysłowu ( `'` ) zamiast `REM` .  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Zobacz też

- [Komentarze w kodzie](../../programming-guide/program-structure/comments-in-code.md)
- [Instrukcje: Przerywanie i łączenie instrukcji w kodzie](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
