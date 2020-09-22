---
title: Sub, wyrażenie
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: e564fa3f717fc1a9f4e9961d9b3e961912a4d56b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873329"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="13177-102">Sub — Wyrażenie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13177-102">Sub Expression (Visual Basic)</span></span>

<span data-ttu-id="13177-103">Deklaruje parametry i kod, który definiuje podprocedure wyrażenie lambda.</span><span class="sxs-lookup"><span data-stu-id="13177-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13177-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="13177-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="13177-105">Części</span><span class="sxs-lookup"><span data-stu-id="13177-105">Parts</span></span>  
  
|<span data-ttu-id="13177-106">Termin</span><span class="sxs-lookup"><span data-stu-id="13177-106">Term</span></span>|<span data-ttu-id="13177-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="13177-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="13177-108">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="13177-108">Optional.</span></span> <span data-ttu-id="13177-109">Lista nazw zmiennych lokalnych, które reprezentują parametry procedury.</span><span class="sxs-lookup"><span data-stu-id="13177-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="13177-110">Nawiasy muszą być obecne nawet wtedy, gdy lista jest pusta.</span><span class="sxs-lookup"><span data-stu-id="13177-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="13177-111">Aby uzyskać więcej informacji, zobacz [Lista parametrów](../statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="13177-111">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="13177-112">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="13177-112">Required.</span></span> <span data-ttu-id="13177-113">Pojedyncza instrukcja.</span><span class="sxs-lookup"><span data-stu-id="13177-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="13177-114">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="13177-114">Required.</span></span> <span data-ttu-id="13177-115">Lista instrukcji.</span><span class="sxs-lookup"><span data-stu-id="13177-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13177-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="13177-116">Remarks</span></span>  

 <span data-ttu-id="13177-117">*Wyrażenie lambda* jest podprocedurą, która nie ma nazwy i która wykonuje co najmniej jedną instrukcję.</span><span class="sxs-lookup"><span data-stu-id="13177-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="13177-118">Wyrażenia lambda można użyć w dowolnym miejscu, w którym można użyć typu delegata, z wyjątkiem argumentu `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="13177-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="13177-119">Aby uzyskać więcej informacji na temat delegatów i użycie wyrażeń lambda z delegatami, zobacz [instrukcja Delegate](../statements/delegate-statement.md) i [Swobodna konwersja delegata](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="13177-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="13177-120">Składnia wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="13177-120">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="13177-121">Składnia wyrażenia lambda jest podobna do standardowej procedury podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="13177-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="13177-122">Różnice są następujące:</span><span class="sxs-lookup"><span data-stu-id="13177-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="13177-123">Wyrażenie lambda nie ma nazwy.</span><span class="sxs-lookup"><span data-stu-id="13177-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="13177-124">Wyrażenie lambda nie może mieć modyfikatora, takiego jak `Overloads` lub `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="13177-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="13177-125">Treść wyrażenia lambda pojedynczego wiersza musi być instrukcją, a nie wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="13177-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="13177-126">Treść może składać się z wywołania procedury Sub, ale nie wywołania procedury funkcji.</span><span class="sxs-lookup"><span data-stu-id="13177-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="13177-127">W wyrażeniu lambda wszystkie parametry muszą mieć określone typy danych lub wszystkie parametry muszą zostać wywnioskowane.</span><span class="sxs-lookup"><span data-stu-id="13177-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="13177-128">Parametry opcjonalne i `ParamArray` są niedozwolone w wyrażeniach lambda.</span><span class="sxs-lookup"><span data-stu-id="13177-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="13177-129">Parametry ogólne są niedozwolone w wyrażeniach lambda.</span><span class="sxs-lookup"><span data-stu-id="13177-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13177-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="13177-130">Example</span></span>  

 <span data-ttu-id="13177-131">Poniżej znajduje się przykład wyrażenia lambda, które zapisuje wartość w konsoli.</span><span class="sxs-lookup"><span data-stu-id="13177-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="13177-132">Przykład pokazuje składnię jednowierszową i wieloliniową wyrażenia lambda dla procedury podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="13177-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="13177-133">Aby uzyskać więcej przykładów, zobacz [lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="13177-133">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="13177-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13177-134">See also</span></span>

- [<span data-ttu-id="13177-135">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="13177-135">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="13177-136">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="13177-136">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="13177-137">Operatory i wyrażenia</span><span class="sxs-lookup"><span data-stu-id="13177-137">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="13177-138">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="13177-138">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="13177-139">Swobodna konwersja delegatów</span><span class="sxs-lookup"><span data-stu-id="13177-139">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
