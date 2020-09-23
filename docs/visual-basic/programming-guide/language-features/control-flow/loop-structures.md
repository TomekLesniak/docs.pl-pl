---
title: Struktury pętli
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 5019eaf219ad70f9c667356636d05ab69fc5a187
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077218"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="e7715-102">Struktury pętli (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7715-102">Loop Structures (Visual Basic)</span></span>

<span data-ttu-id="e7715-103">Struktury pętli Visual Basic umożliwiają powtarzanie jednego lub kilku wierszy kodu.</span><span class="sxs-lookup"><span data-stu-id="e7715-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="e7715-104">Można powtarzać instrukcje w strukturze pętli do momentu, aż do `True` osiągnięcia warunku `False` , określonej liczby razy lub jeden raz dla każdego elementu w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="e7715-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="e7715-105">Poniższa ilustracja przedstawia strukturę pętli, która uruchamia zestaw instrukcji do momentu, gdy zostanie spełniony warunek:</span><span class="sxs-lookup"><span data-stu-id="e7715-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Wykres przepływu, który zawiera element do... Do pętli.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="e7715-107">While — pętle</span><span class="sxs-lookup"><span data-stu-id="e7715-107">While Loops</span></span>  

 <span data-ttu-id="e7715-108">W `While` konstrukcji... `End While` konstrukcja działa zestaw instrukcji, o ile warunek określony w `While` instrukcji to `True` .</span><span class="sxs-lookup"><span data-stu-id="e7715-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="e7715-109">Aby uzyskać więcej informacji, zobacz [while... Instrukcja End while](../../../language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7715-109">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="e7715-110">Pętle do</span><span class="sxs-lookup"><span data-stu-id="e7715-110">Do Loops</span></span>  

 <span data-ttu-id="e7715-111">`Do`Obiekt... `Loop` konstrukcja umożliwia przetestowanie warunku na początku lub na końcu struktury pętli.</span><span class="sxs-lookup"><span data-stu-id="e7715-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="e7715-112">Można również określić, czy pętla ma być powtarzana, gdy warunek pozostanie, `True` lub dopóki się nie stanie `True` .</span><span class="sxs-lookup"><span data-stu-id="e7715-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="e7715-113">Aby uzyskać więcej informacji, zobacz [... Loop — instrukcja](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7715-113">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="e7715-114">Pętle for</span><span class="sxs-lookup"><span data-stu-id="e7715-114">For Loops</span></span>  

 <span data-ttu-id="e7715-115">`For`... `Next` Konstrukcja wykonuje pętlę określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="e7715-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="e7715-116">Używa zmiennej sterującej pętli, zwanej również *licznikiem*, do śledzenia powtórzeń.</span><span class="sxs-lookup"><span data-stu-id="e7715-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="e7715-117">Należy określić wartości początkową i końcową dla tego licznika. Opcjonalnie możesz określić ilość, o którą wzrośnie od jednego powtórzenia do następnego.</span><span class="sxs-lookup"><span data-stu-id="e7715-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="e7715-118">Aby uzyskać więcej informacji, zobacz [dla... Next — instrukcja](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7715-118">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="e7715-119">Dla każdej pętli</span><span class="sxs-lookup"><span data-stu-id="e7715-119">For Each Loops</span></span>  

 <span data-ttu-id="e7715-120">W `For Each` konstrukcji... `Next` konstrukcja uruchamia zestaw instrukcji jeden raz dla każdego elementu w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="e7715-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="e7715-121">Należy określić zmienną sterującą pętli, ale nie trzeba określać jej wartości początkowej ani końcowej.</span><span class="sxs-lookup"><span data-stu-id="e7715-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="e7715-122">Aby uzyskać więcej informacji, zobacz [dla każdej z nich... Next — instrukcja](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7715-122">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7715-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e7715-123">See also</span></span>

- [<span data-ttu-id="e7715-124">Przepływ sterowania</span><span class="sxs-lookup"><span data-stu-id="e7715-124">Control Flow</span></span>](index.md)
- [<span data-ttu-id="e7715-125">Struktury decyzji</span><span class="sxs-lookup"><span data-stu-id="e7715-125">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="e7715-126">Inne struktury sterujące</span><span class="sxs-lookup"><span data-stu-id="e7715-126">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="e7715-127">Zagnieżdżone struktury sterujące</span><span class="sxs-lookup"><span data-stu-id="e7715-127">Nested Control Structures</span></span>](nested-control-structures.md)
