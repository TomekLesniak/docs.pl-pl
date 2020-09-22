---
title: Odwołanie do przyjaznego zestawu „<reference>” jest nieprawidłowe
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874100"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Odwołanie do przyjaznego zestawu „\<reference>” jest nieprawidłowe

Odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe. Zestawy podpisane silnymi nazwami muszą określać klucz publiczny w swoich deklaracjach InternalsVisibleTo.  
  
 Nazwa zestawu przeniesiona do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu identyfikuje zestaw o silnej nazwie, ale nie zawiera `PublicKey` atrybutu.  
  
 **Identyfikator błędu:** BC31535  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Określ klucz publiczny dla zestawu o silnej nazwie zaprzyjaźnionej. Dołącz klucz publiczny jako część nazwy zestawu przesłanej do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu przy użyciu `PublicKey` atrybutu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Reflection.AssemblyName>
- [Zaprzyjaźnione zestawy](../../../standard/assembly/friend.md)
