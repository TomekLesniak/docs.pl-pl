---
title: Element <type1>„<typename>” musi implementować element „<methodname>” dla interfejsu „<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 8bf8872277ec901e066a8b950aaf3e61babfcc48
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872110"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="769f1-102">Element \<type1>„\<typename>” musi implementować element „\<methodname>” dla interfejsu „\<interfacename>”</span><span class="sxs-lookup"><span data-stu-id="769f1-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="769f1-103">Klasa lub struktura oświadczenia do implementacji interfejsu, ale nie implementuje procedury zdefiniowanej przez interfejs.</span><span class="sxs-lookup"><span data-stu-id="769f1-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="769f1-104">Każdy element członkowski interfejsu musi być zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="769f1-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="769f1-105">**Identyfikator błędu:** BC30149</span><span class="sxs-lookup"><span data-stu-id="769f1-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="769f1-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="769f1-106">To correct this error</span></span>  
  
1. <span data-ttu-id="769f1-107">Zadeklaruj procedurę o tej samej nazwie i podpisie, zgodnie z definicją w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="769f1-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="769f1-108">Pamiętaj, aby uwzględnić co najmniej `End Function` instrukcję or `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="769f1-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="769f1-109">Dodaj `Implements` klauzulę do końca `Function` `Sub` instrukcji or.</span><span class="sxs-lookup"><span data-stu-id="769f1-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="769f1-110">Przykład:</span><span class="sxs-lookup"><span data-stu-id="769f1-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="769f1-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="769f1-111">See also</span></span>

- [<span data-ttu-id="769f1-112">Implements — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="769f1-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="769f1-113">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="769f1-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
