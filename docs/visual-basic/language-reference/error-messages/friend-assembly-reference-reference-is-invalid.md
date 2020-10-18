---
title: Odwołanie do przyjaznego zestawu „<reference>” jest nieprawidłowe
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160714"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a>BC31535: odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe

Odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe. Zestawy podpisane silnymi nazwami muszą określać klucz publiczny w swoich deklaracjach InternalsVisibleTo.

 Nazwa zestawu przeniesiona do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu identyfikuje zestaw o silnej nazwie, ale nie zawiera `PublicKey` atrybutu.

 **Identyfikator błędu:** BC31535

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Określ klucz publiczny dla zestawu o silnej nazwie zaprzyjaźnionej. Dołącz klucz publiczny jako część nazwy zestawu przesłanej do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu przy użyciu `PublicKey` atrybutu.

## <a name="see-also"></a>Zobacz też

- <xref:System.Reflection.AssemblyName>
- [Zaprzyjaźnione zestawy](../../../standard/assembly/friend.md)
