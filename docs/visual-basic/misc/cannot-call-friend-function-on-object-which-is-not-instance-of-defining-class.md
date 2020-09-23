---
title: Nie można wywołać funkcji zaprzyjaźnionej dla obiektu, który nie jest wystąpieniem klasy definiującej
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059811"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="3f18a-102">Nie można wywołać funkcji zaprzyjaźnionej dla obiektu, który nie jest wystąpieniem klasy definiującej</span><span class="sxs-lookup"><span data-stu-id="3f18a-102">Cannot call friend function on object which is not an instance of defining class</span></span>

<span data-ttu-id="3f18a-103">Podjęto próbę wywołania `Friend` procedury klasy lub nastąpiła próba uzyskania dostępu do `Friend` właściwości lub metody albo dla wielu wątków.</span><span class="sxs-lookup"><span data-stu-id="3f18a-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="3f18a-104">`Friend`Procedura jest wywoływana z modułu poza klasą, ale jest częścią projektu, w którym jest zdefiniowana Klasa.</span><span class="sxs-lookup"><span data-stu-id="3f18a-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f18a-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="3f18a-105">To correct this error</span></span>  
  
- <span data-ttu-id="3f18a-106">Upewnij się, że wywołujesz lub uzyskujesz dostęp do procedury z modułu, który jest częścią projektu, w którym zdefiniowano klasę.</span><span class="sxs-lookup"><span data-stu-id="3f18a-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f18a-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3f18a-107">See also</span></span>

- [<span data-ttu-id="3f18a-108">Friend</span><span class="sxs-lookup"><span data-stu-id="3f18a-108">Friend</span></span>](../language-reference/modifiers/friend.md)
