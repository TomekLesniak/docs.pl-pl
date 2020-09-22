---
title: Element „<membername>” nie może ujawniać typu „<typename>” poza projektem za pomocą elementu <containertype> „<containertypename>”
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 31d44c93d62163df4d81cb8503b633f0eb317372
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873805"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="dd94a-102">Element „\<membername>” nie może ujawniać typu „\<typename>” poza projektem za pomocą elementu \<containertype> „\<containertypename>”</span><span class="sxs-lookup"><span data-stu-id="dd94a-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="dd94a-103">Zmienna, parametr procedury lub return funkcji jest ujawniany poza kontenerem, ale jest zadeklarowany jako typ, który nie może być ujawniony poza kontenerem.</span><span class="sxs-lookup"><span data-stu-id="dd94a-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="dd94a-104">Poniższy kod szkieletowy przedstawia sytuację, która generuje ten błąd.</span><span class="sxs-lookup"><span data-stu-id="dd94a-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="dd94a-105">Typ, który jest zadeklarowany `Protected` , `Friend` , `Protected Friend` lub `Private` jest przeznaczony do ograniczonego dostępu poza kontekstem deklaracji.</span><span class="sxs-lookup"><span data-stu-id="dd94a-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="dd94a-106">Korzystanie z niego jako typu danych zmiennej z mniejszym ograniczonym dostępem mogłoby spowodować pokonanie tego celu.</span><span class="sxs-lookup"><span data-stu-id="dd94a-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="dd94a-107">W poprzednim kodzie szkieletowym `exposedVar` jest `Public` i uwidacznia `privateClass` kod, który nie powinien mieć do niego dostępu.</span><span class="sxs-lookup"><span data-stu-id="dd94a-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="dd94a-108">**Identyfikator błędu:** BC30909</span><span class="sxs-lookup"><span data-stu-id="dd94a-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd94a-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="dd94a-109">To correct this error</span></span>  
  
- <span data-ttu-id="dd94a-110">Zmień poziom dostępu zmiennej, parametru procedury lub zwracanej funkcji na co najmniej tak restrykcyjny jak poziom dostępu jego typu danych.</span><span class="sxs-lookup"><span data-stu-id="dd94a-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd94a-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dd94a-111">See also</span></span>

- [<span data-ttu-id="dd94a-112">Poziomy dostępu w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd94a-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
