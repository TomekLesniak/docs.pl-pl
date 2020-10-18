---
title: Element „<membername>” nie może ujawniać typu „<typename>” poza projektem za pomocą elementu <containertype> „<containertypename>”
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: a3972eabfe297b89c0e4d0f36943ac58e5bdf688
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162469"
---
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>BC30909: element " \<membername> " nie może ujawniać typu " \<typename> " poza projektem za pomocą \<containertype> " \<containertypename> "

Zmienna, parametr procedury lub return funkcji jest ujawniany poza kontenerem, ale jest zadeklarowany jako typ, który nie może być ujawniony poza kontenerem.

 Poniższy kod szkieletowy przedstawia sytuację, która generuje ten błąd.

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 Typ, który jest zadeklarowany `Protected` , `Friend` , `Protected Friend` lub `Private` jest przeznaczony do ograniczonego dostępu poza kontekstem deklaracji. Korzystanie z niego jako typu danych zmiennej z mniejszym ograniczonym dostępem mogłoby spowodować pokonanie tego celu. W poprzednim kodzie szkieletowym `exposedVar` jest `Public` i uwidacznia `privateClass` kod, który nie powinien mieć do niego dostępu.

 **Identyfikator błędu:** BC30909

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zmień poziom dostępu zmiennej, parametru procedury lub zwracanej funkcji na co najmniej tak restrykcyjny jak poziom dostępu jego typu danych.

## <a name="see-also"></a>Zobacz też

- [Poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
