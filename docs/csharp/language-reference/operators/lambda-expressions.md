---
title: Wyrażenia lambda — odwołanie w C#
description: Informacje o wyrażeniach lambda. Istnieją wyrażenia lambda, które mają wyrażenie jako treść, lub instrukcji lambda, które mają blok instrukcji jako treść.
ms.date: 09/25/2020
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 51bf44af5ec3478f2b2557b047df270c0c22990d
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556845"
---
# <a name="lambda-expressions-c-reference"></a><span data-ttu-id="fefa0-104">Wyrażenia lambda (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="fefa0-104">Lambda expressions (C# reference)</span></span>

<span data-ttu-id="fefa0-105">*Wyrażenie lambda* jest wyrażeniem jednej z następujących dwóch form:</span><span class="sxs-lookup"><span data-stu-id="fefa0-105">A *lambda expression* is an expression of any of the following two forms:</span></span>

- <span data-ttu-id="fefa0-106">[Wyrażenie lambda](#expression-lambdas) , które ma wyrażenie jako treść:</span><span class="sxs-lookup"><span data-stu-id="fefa0-106">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="fefa0-107">[Instrukcja lambda](#statement-lambdas) , która ma blok instrukcji jako treść:</span><span class="sxs-lookup"><span data-stu-id="fefa0-107">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="fefa0-108">Użyj [ `=>` operatora deklaracji lambda](lambda-operator.md) , aby oddzielić listę parametrów lambda z jej treści.</span><span class="sxs-lookup"><span data-stu-id="fefa0-108">Use the [lambda declaration operator `=>`](lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="fefa0-109">Aby utworzyć wyrażenie lambda, należy określić parametry wejściowe (jeśli istnieją) po lewej stronie operatora lambda i wyrażenie lub blok instrukcji po drugiej stronie.</span><span class="sxs-lookup"><span data-stu-id="fefa0-109">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="fefa0-110">Każde wyrażenie lambda można przekonwertować na typ [delegata](../builtin-types/reference-types.md#the-delegate-type) .</span><span class="sxs-lookup"><span data-stu-id="fefa0-110">Any lambda expression can be converted to a [delegate](../builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="fefa0-111">Typ delegata, do którego można przekonwertować wyrażenie lambda, jest definiowany przez typy jego parametrów i wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="fefa0-111">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="fefa0-112">Jeśli wyrażenie lambda nie zwraca wartości, można je przekonwertować na jeden z `Action` typów delegatów; w przeciwnym razie można je przekonwertować na jeden z `Func` typów delegatów.</span><span class="sxs-lookup"><span data-stu-id="fefa0-112">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="fefa0-113">Na przykład wyrażenie lambda, które ma dwa parametry i nie zwraca żadnej wartości, można przekonwertować na <xref:System.Action%602> delegata.</span><span class="sxs-lookup"><span data-stu-id="fefa0-113">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="fefa0-114">Wyrażenie lambda, które ma jeden parametr i zwraca wartość, można przekonwertować na <xref:System.Func%602> obiekt delegowany.</span><span class="sxs-lookup"><span data-stu-id="fefa0-114">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="fefa0-115">W poniższym przykładzie wyrażenie lambda `x => x * x` , które określa parametr o nazwie `x` i zwraca wartość `x` kwadratową, jest przypisywana do zmiennej typu delegata:</span><span class="sxs-lookup"><span data-stu-id="fefa0-115">In the following example, the lambda expression `x => x * x`, which specifies a parameter that's named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="fefa0-116">Wyrażenia lambda można również przekonwertować na typy [drzewa wyrażeń](../../programming-guide/concepts/expression-trees/index.md) , jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="fefa0-116">Expression lambdas can also be converted to the [expression tree](../../programming-guide/concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="fefa0-117">Można użyć wyrażeń lambda w dowolnym kodzie, który wymaga wystąpienia typów delegatów lub drzew wyrażeń, na przykład jako argumentu <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> metody, aby przekazać kod, który powinien być wykonany w tle.</span><span class="sxs-lookup"><span data-stu-id="fefa0-117">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="fefa0-118">Można również użyć wyrażeń lambda podczas pisania [LINQ w języku C#](../../linq/index.md), jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="fefa0-118">You can also use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="fefa0-119">W przypadku użycia składni opartej na metodzie do wywołania <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> metody w <xref:System.Linq.Enumerable?displayProperty=nameWithType> klasie, na przykład w LINQ to Objects i LINQ to XML, parametr jest typem delegata <xref:System.Func%602?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fefa0-119">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fefa0-120">Po wywołaniu <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> metody w <xref:System.Linq.Queryable?displayProperty=nameWithType> klasie, na przykład w LINQ to SQL, typem parametru jest typ drzewa wyrażenia [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>) .</span><span class="sxs-lookup"><span data-stu-id="fefa0-120">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="fefa0-121">W obu przypadkach można użyć tego samego wyrażenia lambda, aby określić wartość parametru.</span><span class="sxs-lookup"><span data-stu-id="fefa0-121">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="fefa0-122">Powoduje to, że dwa `Select` wywołania wyglądają podobnie, chociaż w rzeczywistości typ obiektów utworzonych na podstawie wyrażeń lambda jest różny.</span><span class="sxs-lookup"><span data-stu-id="fefa0-122">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="fefa0-123">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-123">Expression lambdas</span></span>

<span data-ttu-id="fefa0-124">Wyrażenie lambda z wyrażeniem po prawej stronie `=>` operatora jest nazywane *wyrażeniem lambda*.</span><span class="sxs-lookup"><span data-stu-id="fefa0-124">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="fefa0-125">Lambda wyrażenia zwraca wynik wyrażenia i ma następującą podstawową formę:</span><span class="sxs-lookup"><span data-stu-id="fefa0-125">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="fefa0-126">Treść wyrażenia lambda może składać się z wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="fefa0-126">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="fefa0-127">Jednakże w przypadku tworzenia [drzew wyrażeń](../../programming-guide/concepts/expression-trees/index.md) , które są oceniane poza kontekstem środowiska uruchomieniowego języka wspólnego (CLR) platformy .NET, takich jak w SQL Server, nie należy używać wywołań metod w wyrażeniach lambda.</span><span class="sxs-lookup"><span data-stu-id="fefa0-127">However, if you are creating [expression trees](../../programming-guide/concepts/expression-trees/index.md) that are evaluated outside the context of the .NET Common Language Runtime (CLR), such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="fefa0-128">Metody nie będą miały znaczenia poza kontekstem środowiska uruchomieniowego języka wspólnego (CLR) platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fefa0-128">The methods will have no meaning outside the context of the .NET Common Language Runtime (CLR).</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="fefa0-129">Instrukcja lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-129">Statement lambdas</span></span>

<span data-ttu-id="fefa0-130">Instrukcja lambda przypomina wyrażenie lambda, z tą różnicą, że jego instrukcje są ujęte w nawiasy klamrowe:</span><span class="sxs-lookup"><span data-stu-id="fefa0-130">A statement lambda resembles an expression lambda except that its statements are enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="fefa0-131">Treść lambdy instrukcji może składać się z dowolnej liczby instrukcji, jednak w praktyce jest ich zwykle nie więcej niż dwie lub trzy.</span><span class="sxs-lookup"><span data-stu-id="fefa0-131">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatementLambda":::

<span data-ttu-id="fefa0-132">Instrukcji lambda nie można używać do tworzenia drzew wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="fefa0-132">You cannot use statement lambdas to create expression trees.</span></span>

## <a name="input-parameters-of-a-lambda-expression"></a><span data-ttu-id="fefa0-133">Parametry wejściowe wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-133">Input parameters of a lambda expression</span></span>

<span data-ttu-id="fefa0-134">Parametry wejściowe wyrażenia lambda są umieszczane w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="fefa0-134">You enclose input parameters of a lambda expression in parentheses.</span></span> <span data-ttu-id="fefa0-135">Określanie braku parametrów wejściowych za pomocą pustych nawiasów:</span><span class="sxs-lookup"><span data-stu-id="fefa0-135">Specify zero input parameters with empty parentheses:</span></span>  

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetZeroParameters":::

<span data-ttu-id="fefa0-136">Jeśli wyrażenie lambda ma tylko jeden parametr wejściowy, nawiasy są opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="fefa0-136">If a lambda expression has only one input parameter, parentheses are optional:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetOneParameter":::

<span data-ttu-id="fefa0-137">Dwa lub więcej parametrów wejściowych są rozdzielone przecinkami:</span><span class="sxs-lookup"><span data-stu-id="fefa0-137">Two or more input parameters are separated by commas:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetTwoParameters":::

<span data-ttu-id="fefa0-138">Czasami kompilator nie może wywnioskować typów parametrów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="fefa0-138">Sometimes the compiler can't infer the types of input parameters.</span></span> <span data-ttu-id="fefa0-139">Możesz określić typy jawnie, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="fefa0-139">You can specify the types explicitly as shown in the following example:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetExplicitlyTypedParameters":::

<span data-ttu-id="fefa0-140">Typy parametrów wejściowych muszą być jawne lub niejawne; w przeciwnym razie wystąpi błąd kompilatora [CS0748](../../misc/cs0748.md) .</span><span class="sxs-lookup"><span data-stu-id="fefa0-140">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="fefa0-141">Począwszy od języka C# 9,0, można użyć [odrzucania](../../discards.md) , aby określić dwa lub więcej parametrów wejściowych wyrażenia lambda, które nie są używane w wyrażeniu:</span><span class="sxs-lookup"><span data-stu-id="fefa0-141">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of a lambda expression that aren't used in the expression:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetDiscards":::

<span data-ttu-id="fefa0-142">Parametry lambda Discard mogą być przydatne w przypadku używania wyrażenia lambda do [zapewnienia obsługi zdarzeń](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="fefa0-142">Lambda discard parameters may be useful when you use a lambda expression to [provide an event handler](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fefa0-143">W celu zapewnienia zgodności z poprzednimi wersjami, jeśli tylko jeden parametr wejściowy ma nazwę `_` , a następnie, w wyrażeniu lambda, `_` jest traktowany jako nazwa tego parametru.</span><span class="sxs-lookup"><span data-stu-id="fefa0-143">For backwards compatibility, if only a single input parameter is named `_`, then, within a lambda expression, `_` is treated as the name of that parameter.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="fefa0-144">Asynchroniczne wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-144">Async lambdas</span></span>

<span data-ttu-id="fefa0-145">Możesz łatwo tworzyć wyrażenia lambda i instrukcje, które zawierają asynchroniczne przetwarzanie przy użyciu słów kluczowych [Async](../keywords/async.md) i [await](await.md) .</span><span class="sxs-lookup"><span data-stu-id="fefa0-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../keywords/async.md) and [await](await.md) keywords.</span></span> <span data-ttu-id="fefa0-146">Na przykład poniższy Windows Forms przykład zawiera procedurę obsługi zdarzeń, która wywołuje i czeka na metodę asynchroniczną `ExampleMethodAsync` .</span><span class="sxs-lookup"><span data-stu-id="fefa0-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="fefa0-147">Można dodać ten sam program obsługi zdarzeń, używając lambdy asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="fefa0-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="fefa0-148">Aby dodać ten program obsługi, Dodaj `async` modyfikator przed listą parametrów lambda, jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="fefa0-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="fefa0-149">Aby uzyskać więcej informacji na temat tworzenia i używania metod asynchronicznych, zobacz [programowanie asynchroniczne z Async i await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="fefa0-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="fefa0-150">Wyrażenia lambda i krotki</span><span class="sxs-lookup"><span data-stu-id="fefa0-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="fefa0-151">Począwszy od języka C# 7,0, język C# zapewnia wbudowaną obsługę [krotek](../builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="fefa0-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="fefa0-152">Można podać krotkę jako argument wyrażenia lambda, a wyrażenie lambda może również zwracać krotkę.</span><span class="sxs-lookup"><span data-stu-id="fefa0-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="fefa0-153">W niektórych przypadkach kompilator języka C# używa wnioskowania o typie, aby określić typy składników spójnych kolekcji.</span><span class="sxs-lookup"><span data-stu-id="fefa0-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="fefa0-154">Można zdefiniować krotkę, umieszczając w nawiasach rozdzielaną przecinkami listę składników.</span><span class="sxs-lookup"><span data-stu-id="fefa0-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="fefa0-155">Poniższy przykład używa krotki z trzema składnikami, aby przekazać sekwencję liczb do wyrażenia lambda, które podwaja każdą wartość i zwraca spójną kolekcję z trzema składnikami, które zawierają wynik mnożenia.</span><span class="sxs-lookup"><span data-stu-id="fefa0-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="fefa0-156">Zwykle pola krotki mają nazwę `Item1` , `Item2` itp. Można jednak zdefiniować krotkę z nazwanymi składnikami, tak jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="fefa0-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="fefa0-157">Aby uzyskać więcej informacji na temat krotek języka C#, zobacz [typy krotek](../../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="fefa0-157">For more information about C# tuples, see [Tuple types](../../language-reference/builtin-types/value-tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="fefa0-158">Wyrażenia lambda ze standardowymi operatorami zapytań</span><span class="sxs-lookup"><span data-stu-id="fefa0-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="fefa0-159">LINQ to Objects, między innymi implementacjami, mają parametr wejściowy, którego typ jest jedną z <xref:System.Func%601> rodziny delegatów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="fefa0-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="fefa0-160">Te Delegaty używają parametrów typu, aby zdefiniować liczbę i typ parametrów wejściowych oraz zwracany typ delegata.</span><span class="sxs-lookup"><span data-stu-id="fefa0-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="fefa0-161">`Func` Delegaty są bardzo przydatne do hermetyzowania wyrażeń zdefiniowanych przez użytkownika, które są stosowane do każdego elementu w zestawie danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="fefa0-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="fefa0-162">Rozważmy na przykład <xref:System.Func%602> typ delegata:</span><span class="sxs-lookup"><span data-stu-id="fefa0-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="fefa0-163">Delegat można utworzyć jako `Func<int, bool>` wystąpienie, gdzie `int` jest parametrem wejściowym i `bool` jest wartością zwracaną.</span><span class="sxs-lookup"><span data-stu-id="fefa0-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="fefa0-164">Wartość zwracana jest zawsze określona w ostatnim parametrze typu.</span><span class="sxs-lookup"><span data-stu-id="fefa0-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="fefa0-165">Na przykład `Func<int, string, bool>` definiuje delegata z dwoma parametrami wejściowymi `int` i `string` i typem zwracanym `bool` .</span><span class="sxs-lookup"><span data-stu-id="fefa0-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="fefa0-166">Następujący `Func` Delegat, gdy jest wywoływany, zwraca wartość logiczną, która wskazuje, czy parametr wejściowy jest równy pięć:</span><span class="sxs-lookup"><span data-stu-id="fefa0-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="fefa0-167">Można również podać wyrażenie lambda, gdy typem argumentu jest <xref:System.Linq.Expressions.Expression%601> , na przykład w standardowych operatorów zapytań, które są zdefiniowane w <xref:System.Linq.Queryable> typie.</span><span class="sxs-lookup"><span data-stu-id="fefa0-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="fefa0-168">Po określeniu <xref:System.Linq.Expressions.Expression%601> argumentu lambda jest kompilowane do drzewa wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="fefa0-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="fefa0-169">W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Count%2A> standardowego operatora zapytania:</span><span class="sxs-lookup"><span data-stu-id="fefa0-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="fefa0-170">Kompilator może wywnioskować typ parametru wejściowego, ale można go również określić w sposób jawny.</span><span class="sxs-lookup"><span data-stu-id="fefa0-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="fefa0-171">To konkretne wyrażenie lambda liczy te liczby całkowite ( `n` ), które podzielone przez dwa mają resztę 1.</span><span class="sxs-lookup"><span data-stu-id="fefa0-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="fefa0-172">Poniższy przykład tworzy sekwencję zawierającą wszystkie elementy w `numbers` tablicy, która poprzedza 9, ponieważ jest to pierwszy numer w sekwencji, która nie spełnia warunku:</span><span class="sxs-lookup"><span data-stu-id="fefa0-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="fefa0-173">W poniższym przykładzie określono wiele parametrów wejściowych, umieszczając je w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="fefa0-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="fefa0-174">Metoda zwraca wszystkie elementy w `numbers` tablicy do momentu napotkania liczby, której wartość jest mniejsza niż jej pozycja porządkowa w tablicy:</span><span class="sxs-lookup"><span data-stu-id="fefa0-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="fefa0-175">Wnioskowanie o typie w wyrażeniach lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="fefa0-176">Podczas pisania wyrażeń lambda często nie trzeba określać typu parametrów wejściowych, ponieważ kompilator może wywnioskować typ na podstawie treści wyrażenia lambda, typów parametrów i innych czynników, zgodnie z opisem w specyfikacji języka C#.</span><span class="sxs-lookup"><span data-stu-id="fefa0-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="fefa0-177">Dla większości standardowych operatorów zapytań pierwszy element danych wejściowych jest typem elementów w sekwencji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="fefa0-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="fefa0-178">Jeśli wykonujesz zapytania `IEnumerable<Customer>` , wówczas zmienna wejściowa jest wywnioskowana jako `Customer` obiekt, co oznacza, że masz dostęp do jego metod i właściwości:</span><span class="sxs-lookup"><span data-stu-id="fefa0-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="fefa0-179">Ogólne reguły wnioskowania o typie dla wyrażeń lambda są następujące:</span><span class="sxs-lookup"><span data-stu-id="fefa0-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="fefa0-180">Wyrażenie lambda musi zawierać taką samą liczbę parametrów jak typ delegata.</span><span class="sxs-lookup"><span data-stu-id="fefa0-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="fefa0-181">Każdy parametr wejściowy w wyrażeniu lambda musi umożliwiać niejawną konwersję na odpowiadający mu parametr delegata.</span><span class="sxs-lookup"><span data-stu-id="fefa0-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="fefa0-182">Wartość zwracana wyrażenia lambda (jeżeli istnieje) musi umożliwiać niejawną konwersję na zwracany typ delegata.</span><span class="sxs-lookup"><span data-stu-id="fefa0-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="fefa0-183">Należy zauważyć, że wyrażenia lambda same w sobie nie mają typu, ponieważ system typów wspólnych nie ma wewnętrznej koncepcji "wyrażenie lambda".</span><span class="sxs-lookup"><span data-stu-id="fefa0-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="fefa0-184">Jednak czasami wygodnie jest mówić nieformalnie "Type" wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="fefa0-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="fefa0-185">W takich przypadkach typ odwołuje się do typu delegata lub <xref:System.Linq.Expressions.Expression> typu, do którego wyrażenie lambda jest konwertowane.</span><span class="sxs-lookup"><span data-stu-id="fefa0-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="fefa0-186">Przechwycenie zmiennych zewnętrznych i zakresu zmiennych w wyrażeniach lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-186">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="fefa0-187">Wyrażenia lambda mogą odwoływać się do *zmiennych zewnętrznych*.</span><span class="sxs-lookup"><span data-stu-id="fefa0-187">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="fefa0-188">Są to zmienne, które znajdują się w zakresie metody, która definiuje wyrażenie lambda lub w zakresie typu, który zawiera wyrażenie lambda.</span><span class="sxs-lookup"><span data-stu-id="fefa0-188">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="fefa0-189">Przechwytywane w ten sposób zmienne są przechowywane do użytku w wyrażeniu lambda, nawet gdyby w innym wypadku te zmienne znalazłyby się poza zakresem i zostałyby usunięte w ramach odśmiecania pamięci.</span><span class="sxs-lookup"><span data-stu-id="fefa0-189">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="fefa0-190">Zewnętrzna zmienna musi być zdecydowanie przypisana, aby można jej było użyć w wyrażeniu lambda.</span><span class="sxs-lookup"><span data-stu-id="fefa0-190">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="fefa0-191">W poniższym przykładzie pokazano te reguły:</span><span class="sxs-lookup"><span data-stu-id="fefa0-191">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="fefa0-192">Do zakresu zmiennych w wyrażeniach lambda są stosowane następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="fefa0-192">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="fefa0-193">Zmienna, która jest przechwytywana, nie będzie usuwana w ramach odśmiecania pamięci, dopóki odwołujący się do niej delegat nie będzie podlegał odśmiecaniu pamięci.</span><span class="sxs-lookup"><span data-stu-id="fefa0-193">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="fefa0-194">Zmienne wprowadzone w wyrażeniu lambda nie są widoczne w otaczającej metodzie.</span><span class="sxs-lookup"><span data-stu-id="fefa0-194">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="fefa0-195">Wyrażenie lambda nie może bezpośrednio przechwycić parametru [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md)lub [out](../keywords/out-parameter-modifier.md) z otaczającej metody.</span><span class="sxs-lookup"><span data-stu-id="fefa0-195">A lambda expression cannot directly capture an [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md), or [out](../keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="fefa0-196">Instrukcja [Return](../keywords/return.md) w wyrażeniu lambda nie powoduje zwrócenia otaczającej metody.</span><span class="sxs-lookup"><span data-stu-id="fefa0-196">A [return](../keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="fefa0-197">Wyrażenie lambda nie może zawierać instrukcji [goto](../keywords/goto.md), [Break](../keywords/break.md)ani [Continue](../keywords/continue.md) , jeśli element docelowy instrukcji skoku znajduje się poza blokiem wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="fefa0-197">A lambda expression cannot contain a [goto](../keywords/goto.md), [break](../keywords/break.md), or [continue](../keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="fefa0-198">Występuje również błąd instrukcji skoku poza blokiem wyrażenia lambda, jeśli obiekt docelowy znajduje się wewnątrz bloku.</span><span class="sxs-lookup"><span data-stu-id="fefa0-198">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

<span data-ttu-id="fefa0-199">Począwszy od języka C# 9,0, można zastosować `static` modyfikator do wyrażenia lambda, aby zapobiec przypadkowemu przechwyceniu zmiennych lokalnych lub stanu wystąpienia przez wyrażenie lambda:</span><span class="sxs-lookup"><span data-stu-id="fefa0-199">Beginning with C# 9.0, you can apply the `static` modifier to a lambda expression to prevent unintentional capture of local variables or instance state by the lambda:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatic":::

<span data-ttu-id="fefa0-200">Statyczny element lambda nie może przechwycić lokalnych zmiennych lub stanu wystąpienia z otaczających zakresów, ale może odwoływać się do statycznych elementów członkowskich i definicji stałych.</span><span class="sxs-lookup"><span data-stu-id="fefa0-200">A static lambda can't capture local variables or instance state from enclosing scopes, but may reference static members and constant definitions.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fefa0-201">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="fefa0-201">C# language specification</span></span>

<span data-ttu-id="fefa0-202">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fefa0-202">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="fefa0-203">Aby uzyskać więcej informacji na temat funkcji dodanych w języku C# 9,0, zobacz następujące uwagi dotyczące propozycji funkcji:</span><span class="sxs-lookup"><span data-stu-id="fefa0-203">For more information about features added in C# 9.0, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="fefa0-204">Parametry odrzucania wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-204">Lambda discard parameters</span></span>](~/_csharplang/proposals/csharp-9.0/lambda-discard-parameters.md)
- [<span data-ttu-id="fefa0-205">Statyczne funkcje anonimowe</span><span class="sxs-lookup"><span data-stu-id="fefa0-205">Static anonymous functions</span></span>](~/_csharplang/proposals/csharp-9.0/static-anonymous-functions.md)

## <a name="see-also"></a><span data-ttu-id="fefa0-206">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fefa0-206">See also</span></span>

- [<span data-ttu-id="fefa0-207">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="fefa0-207">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fefa0-208">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="fefa0-208">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="fefa0-209">LINQ (zapytanie zintegrowane z językiem)</span><span class="sxs-lookup"><span data-stu-id="fefa0-209">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="fefa0-210">Drzewa wyrażeń</span><span class="sxs-lookup"><span data-stu-id="fefa0-210">Expression Trees</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="fefa0-211">Funkcje lokalne a wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="fefa0-211">Local functions vs. lambda expressions</span></span>](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [<span data-ttu-id="fefa0-212">Visual Studio 2008 — przykłady w języku C# (Zobacz pliki przykładowe zapytania LINQ i program XQuery)</span><span class="sxs-lookup"><span data-stu-id="fefa0-212">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
