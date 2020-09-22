---
title: Element „<keyword>” jest prawidłowy tylko wewnątrz metody wystąpienia
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873901"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>Element „\<keyword>” jest prawidłowy tylko wewnątrz metody wystąpienia

`Me` `MyClass` Słowa kluczowe, i `MyBase` odwołują się do określonych wystąpień klasy. Nie można ich używać wewnątrz wspólnej `Function` procedury lub `Sub` .  
  
 **Identyfikator błędu:** BC30043  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Usuń słowo kluczowe z procedury lub Usuń `Shared` słowo kluczowe z deklaracji procedury.  
  
## <a name="see-also"></a>Zobacz też

- [Przypisanie zmiennej obiektu](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase i MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Podstawowe informacje o dziedziczeniu](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
