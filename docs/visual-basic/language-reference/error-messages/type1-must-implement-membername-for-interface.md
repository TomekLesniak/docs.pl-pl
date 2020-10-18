---
title: Element <type1>„<typename>” musi implementować element „<membername>” dla interfejsu „<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a036097d778daae59ef3bbd74ab8507cd16e6e24
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161858"
---
# <a name="bc30154-type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="49f43-102">BC30154: \<type1> " \<typename> " musi implementować element " \<membername> " dla interfejsu " \<interfacename> "</span><span class="sxs-lookup"><span data-stu-id="49f43-102">BC30154: \<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="49f43-103">element " \<typename> " musi implementować element " \<membername> " dla interfejsu " \<interfacename> ".</span><span class="sxs-lookup"><span data-stu-id="49f43-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="49f43-104">Implementacja właściwości musi mieć pasujące specyfikatory "ReadOnly"/"WriteOnly".</span><span class="sxs-lookup"><span data-stu-id="49f43-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>

 <span data-ttu-id="49f43-105">Klasa lub struktura oświadczenia do implementacji interfejsu, ale nie implementuje procedury, właściwości lub zdarzenia zdefiniowanego przez interfejs.</span><span class="sxs-lookup"><span data-stu-id="49f43-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="49f43-106">Każdy element członkowski interfejsu musi być zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="49f43-106">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="49f43-107">**Identyfikator błędu:** BC30154</span><span class="sxs-lookup"><span data-stu-id="49f43-107">**Error ID:** BC30154</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="49f43-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="49f43-108">To correct this error</span></span>

1. <span data-ttu-id="49f43-109">Zadeklaruj element członkowski o takiej samej nazwie i podpisie, jak zdefiniowano w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="49f43-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="49f43-110">Pamiętaj o uwzględnieniu co najmniej `End Function` instrukcji, `End Sub` , lub `End Property` .</span><span class="sxs-lookup"><span data-stu-id="49f43-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>

2. <span data-ttu-id="49f43-111">Dodaj `Implements` klauzulę na końcu `Function` `Sub` instrukcji,, `Property` lub `Event` .</span><span class="sxs-lookup"><span data-stu-id="49f43-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="49f43-112">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="49f43-112">For example:</span></span>

    ```vb
    Public Event ItHappened() Implements IBaseInterface.ItHappened
    ```

3. <span data-ttu-id="49f43-113">Podczas implementowania właściwości upewnij się, że `ReadOnly` `WriteOnly` jest ona używana w taki sam sposób jak w definicji interfejsu.</span><span class="sxs-lookup"><span data-stu-id="49f43-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>

4. <span data-ttu-id="49f43-114">Podczas implementowania właściwości, deklaracji `Get` i `Set` procedur, zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="49f43-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>

## <a name="see-also"></a><span data-ttu-id="49f43-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49f43-115">See also</span></span>

- [<span data-ttu-id="49f43-116">Implements — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="49f43-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="49f43-117">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="49f43-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
