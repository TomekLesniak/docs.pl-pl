---
title: Drzewa wyrażeń (C#)
description: Dowiedz się więcej na temat drzew wyrażeń. Zapoznaj się z tematem kompilowania i uruchamiania kodu reprezentowanego przez te struktury danych, gdzie każdy węzeł jest wyrażeniem.
ms.date: 07/20/2015
ms.assetid: 7d0ac21a-6d90-4e2e-8903-528cb78615b7
ms.openlocfilehash: 04b5486b6d3c54f0dfd3914eacbda5cffe15890a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167642"
---
# <a name="expression-trees-c"></a><span data-ttu-id="75615-104">Drzewa wyrażeń (C#)</span><span class="sxs-lookup"><span data-stu-id="75615-104">Expression Trees (C#)</span></span>

<span data-ttu-id="75615-105">Drzewa wyrażeń reprezentują kod w strukturze danych przypominającej drzewo, gdzie każdy węzeł jest wyrażeniem, na przykład wywołaniem metody lub operacją binarną, taką jak `x < y` .</span><span class="sxs-lookup"><span data-stu-id="75615-105">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="75615-106">Można skompilować i uruchomić kod reprezentowany przez drzewa wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="75615-106">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="75615-107">Umożliwia to dynamiczną modyfikację kodu wykonywalnego, wykonywanie zapytań LINQ w różnych bazach danych i tworzenie zapytań dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="75615-107">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="75615-108">Aby uzyskać więcej informacji na temat drzew wyrażeń w LINQ, zobacz [jak używać drzew wyrażeń do kompilowania zapytań dynamicznych (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span><span class="sxs-lookup"><span data-stu-id="75615-108">For more information about expression trees in LINQ, see [How to use expression trees to build dynamic queries (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>
  
 <span data-ttu-id="75615-109">Drzewa wyrażeń są również używane w środowisku uruchomieniowym języka dynamicznego (DLR) w celu zapewnienia współdziałania między językami dynamicznymi i .NET oraz umożliwiają autorom kompilatora emitowanie drzew wyrażeń zamiast języka pośredniego firmy Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="75615-109">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and .NET and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="75615-110">Aby uzyskać więcej informacji na temat DLR, zobacz [Omówienie środowiska uruchomieniowego języka dynamicznego](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75615-110">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="75615-111">Można utworzyć drzewo wyrażeń w języku C# lub kompilator Visual Basic na podstawie anonimowego wyrażenia lambda lub można utworzyć drzewa wyrażeń ręcznie przy użyciu <xref:System.Linq.Expressions> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="75615-111">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="75615-112">Tworzenie drzew wyrażeń na podstawie wyrażeń lambda</span><span class="sxs-lookup"><span data-stu-id="75615-112">Creating Expression Trees from Lambda Expressions</span></span>  

 <span data-ttu-id="75615-113">Gdy wyrażenie lambda jest przypisane do zmiennej typu <xref:System.Linq.Expressions.Expression%601> , kompilator emituje kod w celu skompilowania drzewa wyrażenia, które reprezentuje wyrażenie lambda.</span><span class="sxs-lookup"><span data-stu-id="75615-113">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="75615-114">Kompilator języka C# może generować drzewa wyrażeń tylko z wyrażeń lambda (lub jednowierszowych wyrażeń lambda).</span><span class="sxs-lookup"><span data-stu-id="75615-114">The C# compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="75615-115">Nie można analizować instrukcji lambda (lub wielowierszowych wyrażeń lambda).</span><span class="sxs-lookup"><span data-stu-id="75615-115">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="75615-116">Aby uzyskać więcej informacji na temat wyrażeń lambda w języku C#, zobacz [lambda Expressions](../../../language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="75615-116">For more information about lambda expressions in C#, see [Lambda Expressions](../../../language-reference/operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="75615-117">W poniższym przykładzie kodu pokazano, jak utworzyć kompilator języka C#, który reprezentuje wyrażenie lambda `num => num < 5` .</span><span class="sxs-lookup"><span data-stu-id="75615-117">The following code examples demonstrate how to have the C# compiler create an expression tree that represents the lambda expression `num => num < 5`.</span></span>  
  
```csharp  
Expression<Func<int, bool>> lambda = num => num < 5;  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="75615-118">Tworzenie drzew wyrażeń przy użyciu interfejsu API</span><span class="sxs-lookup"><span data-stu-id="75615-118">Creating Expression Trees by Using the API</span></span>  

 <span data-ttu-id="75615-119">Aby utworzyć drzewa wyrażeń przy użyciu interfejsu API, użyj <xref:System.Linq.Expressions.Expression> klasy.</span><span class="sxs-lookup"><span data-stu-id="75615-119">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="75615-120">Ta klasa zawiera statyczne metody fabryki, które tworzą węzły drzewa wyrażenia określonych typów, na przykład, <xref:System.Linq.Expressions.ParameterExpression> która reprezentuje zmienną lub parametr lub <xref:System.Linq.Expressions.MethodCallExpression> , który reprezentuje wywołanie metody.</span><span class="sxs-lookup"><span data-stu-id="75615-120">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="75615-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> i inne typy specyficzne dla wyrażenia są również zdefiniowane w <xref:System.Linq.Expressions> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="75615-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="75615-122">Te typy pochodzą z typu abstrakcyjnego <xref:System.Linq.Expressions.Expression> .</span><span class="sxs-lookup"><span data-stu-id="75615-122">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="75615-123">Poniższy przykład kodu ilustruje sposób tworzenia drzewa wyrażenia, które reprezentuje wyrażenie lambda przy `num => num < 5` użyciu interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="75615-123">The following code example demonstrates how to create an expression tree that represents the lambda expression `num => num < 5` by using the API.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Manually build the expression tree for
// the lambda expression num => num < 5.  
ParameterExpression numParam = Expression.Parameter(typeof(int), "num");  
ConstantExpression five = Expression.Constant(5, typeof(int));  
BinaryExpression numLessThanFive = Expression.LessThan(numParam, five);  
Expression<Func<int, bool>> lambda1 =  
    Expression.Lambda<Func<int, bool>>(  
        numLessThanFive,  
        new ParameterExpression[] { numParam });  
```  
  
 <span data-ttu-id="75615-124">W .NET Framework 4 lub nowszych interfejs API drzew wyrażeń obsługuje również przypisania i wyrażenia przepływu sterowania, takie jak pętle, Bloki warunkowe i `try-catch` bloki.</span><span class="sxs-lookup"><span data-stu-id="75615-124">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="75615-125">Za pomocą interfejsu API można utworzyć drzewa wyrażeń, które są bardziej złożone niż te, które mogą być tworzone na podstawie wyrażeń lambda przez kompilator języka C#.</span><span class="sxs-lookup"><span data-stu-id="75615-125">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the C# compiler.</span></span> <span data-ttu-id="75615-126">Poniższy przykład ilustruje sposób tworzenia drzewa wyrażenia, które oblicza silnię liczby.</span><span class="sxs-lookup"><span data-stu-id="75615-126">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```csharp  
// Creating a parameter expression.  
ParameterExpression value = Expression.Parameter(typeof(int), "value");  
  
// Creating an expression to hold a local variable.
ParameterExpression result = Expression.Parameter(typeof(int), "result");  
  
// Creating a label to jump to from a loop.  
LabelTarget label = Expression.Label(typeof(int));  
  
// Creating a method body.  
BlockExpression block = Expression.Block(  
    // Adding a local variable.  
    new[] { result },  
    // Assigning a constant to a local variable: result = 1  
    Expression.Assign(result, Expression.Constant(1)),  
    // Adding a loop.  
        Expression.Loop(  
    // Adding a conditional block into the loop.  
           Expression.IfThenElse(  
    // Condition: value > 1  
               Expression.GreaterThan(value, Expression.Constant(1)),  
    // If true: result *= value --  
               Expression.MultiplyAssign(result,  
                   Expression.PostDecrementAssign(value)),  
    // If false, exit the loop and go to the label.  
               Expression.Break(label, result)  
           ),  
    // Label to jump to.  
       label  
    )  
);  
  
// Compile and execute an expression tree.  
int factorial = Expression.Lambda<Func<int, int>>(block, value).Compile()(5);  
  
Console.WriteLine(factorial);  
// Prints 120.  
```

<span data-ttu-id="75615-127">Aby uzyskać więcej informacji, zobacz [generowanie metod dynamicznych z drzewami wyrażeń w programie Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), które mają zastosowanie również do nowszych wersji programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75615-127">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="75615-128">Analizowanie drzew wyrażeń</span><span class="sxs-lookup"><span data-stu-id="75615-128">Parsing Expression Trees</span></span>  

 <span data-ttu-id="75615-129">Poniższy przykład kodu demonstruje, jak drzewo wyrażeń reprezentujące wyrażenie lambda `num => num < 5` może być rozłożone na jego części.</span><span class="sxs-lookup"><span data-stu-id="75615-129">The following code example demonstrates how the expression tree that represents the lambda expression `num => num < 5` can be decomposed into its parts.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Create an expression tree.  
Expression<Func<int, bool>> exprTree = num => num < 5;  
  
// Decompose the expression tree.  
ParameterExpression param = (ParameterExpression)exprTree.Parameters[0];  
BinaryExpression operation = (BinaryExpression)exprTree.Body;  
ParameterExpression left = (ParameterExpression)operation.Left;  
ConstantExpression right = (ConstantExpression)operation.Right;  
  
Console.WriteLine("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value);  
  
// This code produces the following output:  
  
// Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="75615-130">Niezmienności drzew wyrażeń</span><span class="sxs-lookup"><span data-stu-id="75615-130">Immutability of Expression Trees</span></span>  

 <span data-ttu-id="75615-131">Drzewa wyrażeń powinny być niezmienne.</span><span class="sxs-lookup"><span data-stu-id="75615-131">Expression trees should be immutable.</span></span> <span data-ttu-id="75615-132">Oznacza to, że jeśli chcesz zmodyfikować drzewo wyrażenia, należy utworzyć nowe drzewo wyrażeń przez skopiowanie istniejącego i zastępowanie węzłów w tym elemencie.</span><span class="sxs-lookup"><span data-stu-id="75615-132">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="75615-133">Możesz użyć odwiedzania drzewa wyrażenia, aby przejść do istniejącego drzewa wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="75615-133">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="75615-134">Aby uzyskać więcej informacji, zobacz [jak modyfikować drzewa wyrażeń (C#)](./how-to-modify-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="75615-134">For more information, see [How to modify expression trees (C#)](./how-to-modify-expression-trees.md).</span></span>
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="75615-135">Kompilowanie drzew wyrażeń</span><span class="sxs-lookup"><span data-stu-id="75615-135">Compiling Expression Trees</span></span>  

 <span data-ttu-id="75615-136"><xref:System.Linq.Expressions.Expression%601>Typ udostępnia <xref:System.Linq.Expressions.Expression%601.Compile%2A> metodę, która kompiluje kod reprezentowany przez drzewo wyrażenia w delegatze pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="75615-136">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="75615-137">Poniższy przykład kodu demonstruje sposób kompilowania drzewa wyrażenia i uruchamiania wyniku.</span><span class="sxs-lookup"><span data-stu-id="75615-137">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```csharp  
// Creating an expression tree.  
Expression<Func<int, bool>> expr = num => num < 5;  
  
// Compiling the expression tree into a delegate.  
Func<int, bool> result = expr.Compile();  
  
// Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4));  
  
// Prints True.  
  
// You can also use simplified syntax  
// to compile and run an expression tree.  
// The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4));  
  
// Also prints True.  
```  
  
 <span data-ttu-id="75615-138">Aby uzyskać więcej informacji, zobacz [jak wykonywać drzewa wyrażeń (C#)](./how-to-execute-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="75615-138">For more information, see [How to execute expression trees (C#)](./how-to-execute-expression-trees.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75615-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75615-139">See also</span></span>

- <xref:System.Linq.Expressions>
- [<span data-ttu-id="75615-140">Wykonywanie drzew wyrażeń (C#)</span><span class="sxs-lookup"><span data-stu-id="75615-140">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="75615-141">Jak zmodyfikować drzewa wyrażeń (C#)</span><span class="sxs-lookup"><span data-stu-id="75615-141">How to modify expression trees (C#)</span></span>](./how-to-modify-expression-trees.md)
- [<span data-ttu-id="75615-142">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="75615-142">Lambda Expressions</span></span>](../../../language-reference/operators/lambda-expressions.md)
- [<span data-ttu-id="75615-143">Omówienie środowiska uruchomieniowego języka dynamicznego</span><span class="sxs-lookup"><span data-stu-id="75615-143">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="75615-144">Koncepcje programowania (C#)</span><span class="sxs-lookup"><span data-stu-id="75615-144">Programming Concepts (C#)</span></span>](../index.md)
