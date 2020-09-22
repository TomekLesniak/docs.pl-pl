---
title: Klasa obiektu delegowanego „<classname>” nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874492"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="cdbc7-102">Klasa obiektu delegowanego „\<classname>” nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody</span><span class="sxs-lookup"><span data-stu-id="cdbc7-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="cdbc7-103">Wywołanie `Invoke` za pomocą delegata nie powiodło się `Invoke` , ponieważ nie jest zaimplementowany w klasie delegata.</span><span class="sxs-lookup"><span data-stu-id="cdbc7-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="cdbc7-104">**Identyfikator błędu:** BC30220</span><span class="sxs-lookup"><span data-stu-id="cdbc7-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cdbc7-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="cdbc7-105">To correct this error</span></span>  
  
1. <span data-ttu-id="cdbc7-106">Upewnij się, że wystąpienie klasy Delegate zostało utworzone z `Dim` instrukcją i że procedura została przypisana do wystąpienia delegata z `AddressOf` operatorem.</span><span class="sxs-lookup"><span data-stu-id="cdbc7-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="cdbc7-107">Znajdź kod implementujący klasę delegata i upewnij się, że implementuje `Invoke` procedurę.</span><span class="sxs-lookup"><span data-stu-id="cdbc7-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbc7-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cdbc7-108">See also</span></span>

- [<span data-ttu-id="cdbc7-109">Delegaci</span><span class="sxs-lookup"><span data-stu-id="cdbc7-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="cdbc7-110">Delegate — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="cdbc7-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="cdbc7-111">AddressOf, operator</span><span class="sxs-lookup"><span data-stu-id="cdbc7-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="cdbc7-112">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="cdbc7-112">Dim Statement</span></span>](../statements/dim-statement.md)
