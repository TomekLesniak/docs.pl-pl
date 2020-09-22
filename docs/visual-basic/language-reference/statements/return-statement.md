---
title: Return, instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 3ca705409bc8233bc2562c64b8e7704f08dd7641
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871807"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="067ac-102">Return — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="067ac-102">Return Statement (Visual Basic)</span></span>

<span data-ttu-id="067ac-103">Zwraca kontrolę do kodu, który wywołał `Function` `Sub` procedurę,,, `Get` `Set` lub `Operator` .</span><span class="sxs-lookup"><span data-stu-id="067ac-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="067ac-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="067ac-105">Część</span><span class="sxs-lookup"><span data-stu-id="067ac-105">Part</span></span>  

 `expression`  
 <span data-ttu-id="067ac-106">Wymagane w `Function` procedurze, `Get` lub `Operator` .</span><span class="sxs-lookup"><span data-stu-id="067ac-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="067ac-107">Wyrażenie, które reprezentuje wartość, która ma zostać zwrócona do kodu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="067ac-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067ac-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="067ac-108">Remarks</span></span>  

 <span data-ttu-id="067ac-109">W `Sub` procedurze lub `Set` `Return` instrukcja jest równoznaczna z `Exit Sub` `Exit Property` instrukcją or i `expression` nie może być dostarczone.</span><span class="sxs-lookup"><span data-stu-id="067ac-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="067ac-110">W `Function` procedurze, `Get` , lub `Operator` , `Return` instrukcja musi zawierać `expression` , i `expression` musi oszacować do typu danych, który jest konwertowany na zwracany typ procedury.</span><span class="sxs-lookup"><span data-stu-id="067ac-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="067ac-111">W `Function` procedurze lub `Get` można także przypisać wyrażenie do nazwy procedury, która ma stanowić wartość zwracaną, a następnie wykonuje `Exit Function` `Exit Property` instrukcję or.</span><span class="sxs-lookup"><span data-stu-id="067ac-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="067ac-112">W `Operator` procedurze należy użyć `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="067ac-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="067ac-113">`Return`W tej samej procedurze można dołączyć dowolną liczbę instrukcji.</span><span class="sxs-lookup"><span data-stu-id="067ac-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="067ac-114">Kod w bloku jest `Finally` uruchamiany po `Return` `Try` napotkaniu instrukcji w bloku lub `Catch` , ale przed wykonaniem tej `Return` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="067ac-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="067ac-115">`Return`Instrukcja nie może być uwzględniona w `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="067ac-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="067ac-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="067ac-116">Example</span></span>  

 <span data-ttu-id="067ac-117">Poniższy przykład używa `Return` instrukcji kilka razy, aby powrócić do kodu wywołującego, gdy procedura nie musi wykonywać żadnych innych czynności.</span><span class="sxs-lookup"><span data-stu-id="067ac-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="067ac-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="067ac-118">See also</span></span>

- [<span data-ttu-id="067ac-119">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="067ac-120">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="067ac-121">Get — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="067ac-122">Set — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="067ac-123">Operator — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="067ac-124">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="067ac-125">Exit, instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="067ac-126">Try...Catch...Finally, instrukcja</span><span class="sxs-lookup"><span data-stu-id="067ac-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
