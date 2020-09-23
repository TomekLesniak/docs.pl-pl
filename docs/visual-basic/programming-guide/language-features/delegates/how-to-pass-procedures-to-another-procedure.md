---
title: 'Instrukcje: przekazywanie procedur do innej procedury'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 3a7a653bbf238b50e3c7339da76df0f68ab9b59f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085792"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="2a6c3-102">Porady: przekazywanie procedur do innej procedury w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a6c3-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>

<span data-ttu-id="2a6c3-103">Ten przykład pokazuje, jak za pomocą delegatów przekazać procedurę do innej procedury.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="2a6c3-104">Delegat jest typem, który można użyć jak dowolnego innego typu w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="2a6c3-105">`AddressOf`Operator zwraca obiekt delegata w przypadku zastosowania do nazwy procedury.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="2a6c3-106">Ten przykład zawiera procedurę z parametrem delegata, który może odwoływać się do innej procedury uzyskanej przy użyciu `AddressOf` operatora.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="2a6c3-107">Tworzenie procedur delegat i Matching</span><span class="sxs-lookup"><span data-stu-id="2a6c3-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="2a6c3-108">Utwórz delegata o nazwie `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="2a6c3-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="2a6c3-109">Utwórz procedurę o nazwie `AddNumbers` z parametrami i zwracaną wartością zgodną z tymi `MathOperator` , aby podpisy były zgodne.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="2a6c3-110">Utwórz procedurę o nazwie `SubtractNumbers` z podpisem pasującym do `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="2a6c3-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="2a6c3-111">Utwórz procedurę o nazwie `DelegateTest` , która przyjmuje delegat jako parametr.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="2a6c3-112">Ta procedura może akceptować odwołanie do `AddNumbers` lub `SubtractNumbers` , ponieważ ich podpisy pasują do `MathOperator` podpisu.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="2a6c3-113">Utwórz procedurę o nazwie `Test` , która wywołuje `DelegateTest` jeden raz z delegatem `AddNumbers` jako parametr i ponownie z delegatem `SubtractNumbers` jako parametr.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="2a6c3-114">Gdy `Test` jest wywoływana, najpierw wyświetla wynik działania `AddNumbers` w `5` i `3` , czyli 8.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="2a6c3-115">Następnie zostanie wyświetlony wynik działania `SubtractNumbers` w dniu `9` i, czyli `3` 6.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6c3-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2a6c3-116">See also</span></span>

- [<span data-ttu-id="2a6c3-117">Delegaci</span><span class="sxs-lookup"><span data-stu-id="2a6c3-117">Delegates</span></span>](index.md)
- [<span data-ttu-id="2a6c3-118">AddressOf, operator</span><span class="sxs-lookup"><span data-stu-id="2a6c3-118">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="2a6c3-119">Delegate — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="2a6c3-119">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="2a6c3-120">Instrukcje: wywoływanie metody delegata</span><span class="sxs-lookup"><span data-stu-id="2a6c3-120">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)
