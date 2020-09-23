---
title: 'Porady: wywoływanie procedury zwracającej wartość'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 53589f84c6675d1e7ae2a593341e5dac747132a9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083980"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="82e8a-102">Porady: wywoływanie procedury zwracającej wartość (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82e8a-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="82e8a-103">`Function`Procedura zwraca wartość do kodu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="82e8a-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="82e8a-104">Należy to wywołać, dołączając jego nazwę i argumenty po prawej stronie instrukcji przypisania lub w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="82e8a-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="82e8a-105">Aby wywołać procedurę funkcji w wyrażeniu</span><span class="sxs-lookup"><span data-stu-id="82e8a-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="82e8a-106">Użyj `Function` nazwy procedury w taki sam sposób, jak w przypadku użycia zmiennej.</span><span class="sxs-lookup"><span data-stu-id="82e8a-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="82e8a-107">Możesz użyć `Function` wywołania procedury wszędzie tam, gdzie można użyć zmiennej lub stałej w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="82e8a-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="82e8a-108">Postępuj zgodnie z nazwą procedury z nawiasami, aby ująć listę argumentów.</span><span class="sxs-lookup"><span data-stu-id="82e8a-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="82e8a-109">Jeśli nie ma żadnych argumentów, możesz opcjonalnie pominąć nawiasy.</span><span class="sxs-lookup"><span data-stu-id="82e8a-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="82e8a-110">Jednak użycie nawiasów sprawia, że kod można ułatwić odczytywanie.</span><span class="sxs-lookup"><span data-stu-id="82e8a-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="82e8a-111">Umieść argumenty na liście argumentów w nawiasach rozdzielonych przecinkami.</span><span class="sxs-lookup"><span data-stu-id="82e8a-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="82e8a-112">Upewnij się, że podasz argumenty w tej samej kolejności, w której `Function` procedura definiuje odpowiednie parametry.</span><span class="sxs-lookup"><span data-stu-id="82e8a-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="82e8a-113">Alternatywnie można przekazać jeden lub więcej argumentów według nazwy.</span><span class="sxs-lookup"><span data-stu-id="82e8a-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="82e8a-114">Aby uzyskać więcej informacji, zobacz [przekazywanie argumentów według pozycji i według nazwy](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="82e8a-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="82e8a-115">Wartość zwrócona przez procedurę uczestniczy w wyrażeniu tak samo jak wartość zmiennej lub stałej.</span><span class="sxs-lookup"><span data-stu-id="82e8a-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="82e8a-116">Aby wywołać procedurę funkcji w instrukcji przypisania</span><span class="sxs-lookup"><span data-stu-id="82e8a-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="82e8a-117">Użyj `Function` nazwy procedury po znaku równości ( `=` ) w instrukcji przypisania.</span><span class="sxs-lookup"><span data-stu-id="82e8a-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="82e8a-118">Postępuj zgodnie z nazwą procedury z nawiasami, aby ująć listę argumentów.</span><span class="sxs-lookup"><span data-stu-id="82e8a-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="82e8a-119">Jeśli nie ma żadnych argumentów, możesz opcjonalnie pominąć nawiasy.</span><span class="sxs-lookup"><span data-stu-id="82e8a-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="82e8a-120">Jednak użycie nawiasów sprawia, że kod można ułatwić odczytywanie.</span><span class="sxs-lookup"><span data-stu-id="82e8a-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="82e8a-121">Umieść argumenty na liście argumentów w nawiasach rozdzielonych przecinkami.</span><span class="sxs-lookup"><span data-stu-id="82e8a-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="82e8a-122">Upewnij się, że podasz argumenty w tej samej kolejności, w jakiej `Function` procedura definiuje odpowiednie parametry, chyba że przekazujesz je według nazwy.</span><span class="sxs-lookup"><span data-stu-id="82e8a-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="82e8a-123">Wartość zwracana z procedury jest przechowywana w zmiennej lub właściwości po lewej stronie instrukcji przypisania.</span><span class="sxs-lookup"><span data-stu-id="82e8a-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82e8a-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="82e8a-124">Example</span></span>  

 <span data-ttu-id="82e8a-125">Poniższy przykład wywołuje Visual Basic, <xref:Microsoft.VisualBasic.Interaction.Environ%2A> Aby pobrać wartość zmiennej środowiskowej systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="82e8a-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="82e8a-126">Pierwszy wiersz wywołuje `Environ` wewnątrz wyrażenia, a drugi wiersz wywołuje go w instrukcji przypisania.</span><span class="sxs-lookup"><span data-stu-id="82e8a-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="82e8a-127">`Environ` przyjmuje nazwę zmiennej jako jedynego argumentu.</span><span class="sxs-lookup"><span data-stu-id="82e8a-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="82e8a-128">Zwraca wartość zmiennej do kodu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="82e8a-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="82e8a-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="82e8a-129">See also</span></span>

- [<span data-ttu-id="82e8a-130">Procedury funkcji</span><span class="sxs-lookup"><span data-stu-id="82e8a-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="82e8a-131">Parametry i argumenty procedur</span><span class="sxs-lookup"><span data-stu-id="82e8a-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="82e8a-132">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="82e8a-132">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="82e8a-133">Instrukcje: tworzenie procedury, która zwraca wartość</span><span class="sxs-lookup"><span data-stu-id="82e8a-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="82e8a-134">Porady: zwracanie wartości z procedury</span><span class="sxs-lookup"><span data-stu-id="82e8a-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="82e8a-135">Porady: wywoływanie procedury, która nie zwraca wartości</span><span class="sxs-lookup"><span data-stu-id="82e8a-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
