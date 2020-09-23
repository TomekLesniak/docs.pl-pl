---
title: 'Porady: tworzenie i dodawanie metody rozszerzania wykorzystywanej przez inicjator kolekcji'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: c36fab6635a9f7820c52c5f73c20487b92879b9a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086351"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Porady: tworzenie i dodawanie metody rozszerzania wykorzystywanej przez inicjator kolekcji (Visual Basic)

W przypadku tworzenia kolekcji za pomocą inicjatora kolekcji, kompilator Visual Basic wyszukuje `Add` metodę typu kolekcji, dla którego parametry `Add` metody pasują do typów wartości w inicjatorze kolekcji. Ta `Add` Metoda służy do wypełniania kolekcji wartościami z inicjatora kolekcji.  
  
 Jeśli żadna zgodna `Add` Metoda nie istnieje i nie można zmodyfikować kodu dla kolekcji, można dodać metodę rozszerzenia o nazwie `Add` , która pobiera parametry wymagane przez inicjator kolekcji. Zazwyczaj jest to konieczne, gdy do kolekcji ogólnych są używane Inicjatory kolekcji.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak dodać metodę rozszerzenia do typu ogólnego, <xref:System.Collections.Generic.List%601> Aby inicjator kolekcji mógł służyć do dodawania obiektów typu `Employee` . Metoda rozszerzenia umożliwia użycie skróconej składni inicjatora kolekcji.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz także

- [Inicjatory kolekcji](index.md)
- [Instrukcje: tworzenie kolekcji używanej przez inicjator kolekcji](how-to-create-a-collection-used-by-a-collection-initializer.md)
