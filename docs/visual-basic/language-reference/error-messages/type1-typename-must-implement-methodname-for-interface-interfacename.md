---
title: Element <type1>„<typename>” musi implementować element „<methodname>” dla interfejsu „<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161871"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="42869-102">BC30149: \<type1> " \<typename> " musi implementować element " \<methodname> " dla interfejsu " \<interfacename> "</span><span class="sxs-lookup"><span data-stu-id="42869-102">BC30149: \<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="42869-103">Klasa lub struktura oświadczenia do implementacji interfejsu, ale nie implementuje procedury zdefiniowanej przez interfejs.</span><span class="sxs-lookup"><span data-stu-id="42869-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="42869-104">Każdy element członkowski interfejsu musi być zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="42869-104">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="42869-105">**Identyfikator błędu:** BC30149</span><span class="sxs-lookup"><span data-stu-id="42869-105">**Error ID:** BC30149</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="42869-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="42869-106">To correct this error</span></span>

1. <span data-ttu-id="42869-107">Zadeklaruj procedurę o tej samej nazwie i podpisie, zgodnie z definicją w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="42869-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="42869-108">Pamiętaj, aby uwzględnić co najmniej `End Function` instrukcję or `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="42869-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="42869-109">Dodaj `Implements` klauzulę do końca `Function` `Sub` instrukcji or.</span><span class="sxs-lookup"><span data-stu-id="42869-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="42869-110">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="42869-110">For example:</span></span>

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a><span data-ttu-id="42869-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="42869-111">See also</span></span>

- [<span data-ttu-id="42869-112">Implements — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="42869-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="42869-113">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="42869-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
