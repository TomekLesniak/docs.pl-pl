---
title: Referencje i instrukcja Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 13f250e1b015e5a821da83e557033bc878a8a3b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097907"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Referencje i importy — Instrukcja (Visual Basic)

Obiekty zewnętrzne można udostępnić projekt, wybierając polecenie **Dodaj odwołanie** w menu **projekt** . Odwołania w Visual Basic mogą wskazywać zestawy, które są takie jak biblioteki typów, ale zawierają więcej informacji.  
  
## <a name="the-imports-statement"></a>Instrukcja Imports  

 Zestawy obejmują co najmniej jedną przestrzeń nazw. Po dodaniu odwołania do zestawu, można również dodać `Imports` instrukcję do modułu, który kontroluje widoczność przestrzeni nazw tego zestawu w module. `Imports`Instrukcja zawiera kontekst zakresu, który umożliwia użycie tylko części przestrzeni nazw niezbędnej do dostarczenia unikatowego odwołania.  
  
 `Imports`Instrukcja ma następującą składnię:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` odwołuje się do krótkiej nazwy, której można użyć w kodzie, aby odwołać się do zaimportowanej przestrzeni nazw. `Namespace` jest przestrzenią nazw dostępną za pomocą odwołania do projektu, za pomocą definicji w ramach projektu lub poprzedniej `Imports` instrukcji.  
  
 Moduł może zawierać dowolną liczbę `Imports` instrukcji. Muszą one znajdować się po każdej `Option` instrukcji, jeśli jest obecny, ale przed jakimkolwiek innym kodem.  
  
> [!NOTE]
> Nie należy mylić odwołań projektu z `Imports` instrukcją lub `Declare` instrukcją. Odwołania projektu tworzą obiekty zewnętrzne, takie jak obiekty w zestawach, dostępne do Visual Basic projektów. `Imports`Instrukcja służy do uproszczenia dostępu do odwołań do projektu, ale nie zapewnia dostępu do tych obiektów. `Declare`Instrukcja jest używana do deklarowania odwołania do procedury zewnętrznej w bibliotece dołączanej dynamicznie (dll).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Używanie aliasów z instrukcją Imports  

 `Imports`Instrukcja ułatwia dostęp do metod klas przez wyeliminowanie konieczności jawnego wpisywania w pełni kwalifikowanych nazw odwołań. Aliasy umożliwiają przypisanie nazwy bardziej przyjaznej tylko do jednej części przestrzeni nazw. Na przykład sekwencja powrotu karetki i wysuwu wiersza, która powoduje, że pojedynczy fragment tekstu, który ma być wyświetlany w wielu wierszach, jest częścią <xref:Microsoft.VisualBasic.ControlChars> modułu w <xref:Microsoft.VisualBasic?displayProperty=nameWithType> przestrzeni nazw. Aby użyć tej stałej w programie bez aliasu, należy wpisać następujący kod:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` instrukcje muszą zawsze być pierwszym wierszem bezpośrednio po `Option` instrukcjach w module. Poniższy fragment kodu przedstawia sposób importowania i przypisywania aliasu do <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modułu:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Przyszłe odwołania do tej przestrzeni nazw mogą być znacznie krótsze:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Jeśli `Imports` instrukcja nie zawiera nazwy aliasu, elementy zdefiniowane w zaimportowanej przestrzeni nazw mogą być używane w module bez kwalifikacji. Jeśli Nazwa aliasu jest określona, musi być używana jako kwalifikator dla nazw zawartych w tej przestrzeni nazw.  
  
## <a name="see-also"></a>Zobacz także

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Przestrzenie nazw w Visual Basic](namespaces.md)
- [Zestawy w środowisku .NET](../../../standard/assembly/index.md)
- [Imports — Instrukcja (.NET Namespace i Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
