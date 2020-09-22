---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: c2dcb044d04099c51f57d82a8bc08f0932bf3542
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875423"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="9b0e3-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b0e3-102">WithEvents (Visual Basic)</span></span>

<span data-ttu-id="9b0e3-103">Określa, że co najmniej jedna zadeklarowana zmienna składowej odnosi się do wystąpienia klasy, która może zgłaszać zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b0e3-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9b0e3-104">Remarks</span></span>

<span data-ttu-id="9b0e3-105">Gdy zmienna jest zdefiniowana przy użyciu `WithEvents` , można deklaratywnie określić, że metoda obsługuje zdarzenia zmiennej przy użyciu `Handles` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="9b0e3-106">Można używać `WithEvents` tylko na poziomie klasy lub modułu.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="9b0e3-107">Oznacza to, że kontekst deklaracji dla `WithEvents` zmiennej musi być klasą lub modułem i nie może być plikiem źródłowym, przestrzenią nazw, strukturą ani procedurą.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="9b0e3-108">Nie można użyć `WithEvents` w składowej struktury.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="9b0e3-109">Można zadeklarować tylko pojedyncze zmienne — nie tablice — za pomocą `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="9b0e3-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="9b0e3-110">Reguły</span><span class="sxs-lookup"><span data-stu-id="9b0e3-110">Rules</span></span>

<span data-ttu-id="9b0e3-111">**Typy elementów.**</span><span class="sxs-lookup"><span data-stu-id="9b0e3-111">**Element Types.**</span></span> <span data-ttu-id="9b0e3-112">Należy zadeklarować `WithEvents` zmienne jako zmienne obiektów, aby mogły akceptować wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="9b0e3-113">Nie można jednak zadeklarować ich jako `Object` .</span><span class="sxs-lookup"><span data-stu-id="9b0e3-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="9b0e3-114">Należy zadeklarować je jako konkretną klasę, która może zgłaszać zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="9b0e3-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="9b0e3-115">`WithEvents`Modyfikator może być używany w tym kontekście: [Dim — Instrukcja](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9b0e3-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="9b0e3-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="9b0e3-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="9b0e3-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b0e3-117">See also</span></span>

- [<span data-ttu-id="9b0e3-118">Handles</span><span class="sxs-lookup"><span data-stu-id="9b0e3-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="9b0e3-119">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="9b0e3-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="9b0e3-120">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="9b0e3-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
