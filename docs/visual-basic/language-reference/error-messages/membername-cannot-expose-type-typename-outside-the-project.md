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
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="748c2-102">BC30909: element " \<membername> " nie może ujawniać typu " \<typename> " poza projektem za pomocą \<containertype> " \<containertypename> "</span><span class="sxs-lookup"><span data-stu-id="748c2-102">BC30909: '\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="748c2-103">Zmienna, parametr procedury lub return funkcji jest ujawniany poza kontenerem, ale jest zadeklarowany jako typ, który nie może być ujawniony poza kontenerem.</span><span class="sxs-lookup"><span data-stu-id="748c2-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>

 <span data-ttu-id="748c2-104">Poniższy kod szkieletowy przedstawia sytuację, która generuje ten błąd.</span><span class="sxs-lookup"><span data-stu-id="748c2-104">The following skeleton code shows a situation that generates this error.</span></span>

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 <span data-ttu-id="748c2-105">Typ, który jest zadeklarowany `Protected` , `Friend` , `Protected Friend` lub `Private` jest przeznaczony do ograniczonego dostępu poza kontekstem deklaracji.</span><span class="sxs-lookup"><span data-stu-id="748c2-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="748c2-106">Korzystanie z niego jako typu danych zmiennej z mniejszym ograniczonym dostępem mogłoby spowodować pokonanie tego celu.</span><span class="sxs-lookup"><span data-stu-id="748c2-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="748c2-107">W poprzednim kodzie szkieletowym `exposedVar` jest `Public` i uwidacznia `privateClass` kod, który nie powinien mieć do niego dostępu.</span><span class="sxs-lookup"><span data-stu-id="748c2-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>

 <span data-ttu-id="748c2-108">**Identyfikator błędu:** BC30909</span><span class="sxs-lookup"><span data-stu-id="748c2-108">**Error ID:** BC30909</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="748c2-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="748c2-109">To correct this error</span></span>

- <span data-ttu-id="748c2-110">Zmień poziom dostępu zmiennej, parametru procedury lub zwracanej funkcji na co najmniej tak restrykcyjny jak poziom dostępu jego typu danych.</span><span class="sxs-lookup"><span data-stu-id="748c2-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="748c2-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="748c2-111">See also</span></span>

- [<span data-ttu-id="748c2-112">Poziomy dostępu w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="748c2-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
