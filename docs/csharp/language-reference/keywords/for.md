---
description: for — odwołanie w C#
title: for — odwołanie w C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: be9ecdc08d54c9cde1c49656a16e0d85a6d7084d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126934"
---
# <a name="for-c-reference"></a><span data-ttu-id="f851f-103">for (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="f851f-103">for (C# reference)</span></span>

<span data-ttu-id="f851f-104">`for`Instrukcja wykonuje instrukcję lub blok instrukcji, gdy określone wyrażenie logiczne zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="f851f-104">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="f851f-105">W dowolnym momencie w `for` bloku instrukcji można przerwać pętlę przy użyciu instrukcji [Break](break.md) lub przejść do następnej iteracji w pętli przy użyciu instrukcji [Continue](continue.md) .</span><span class="sxs-lookup"><span data-stu-id="f851f-105">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="f851f-106">Możesz również wyjść z `for` pętli przez instrukcje [goto](goto.md), [Return](return.md)lub [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="f851f-106">You can also exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="f851f-107">Struktura `for` instrukcji</span><span class="sxs-lookup"><span data-stu-id="f851f-107">Structure of the `for` statement</span></span>

<span data-ttu-id="f851f-108">`for`Instrukcja definiuje *inicjator*, *warunek*i sekcje *iteratora* :</span><span class="sxs-lookup"><span data-stu-id="f851f-108">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="f851f-109">Wszystkie trzy sekcje są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="f851f-109">All three sections are optional.</span></span> <span data-ttu-id="f851f-110">Treść pętli jest instrukcją lub blokiem instrukcji.</span><span class="sxs-lookup"><span data-stu-id="f851f-110">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="f851f-111">Poniższy przykład pokazuje `for` instrukcję ze wszystkimi zdefiniowanymi sekcjami:</span><span class="sxs-lookup"><span data-stu-id="f851f-111">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](snippets/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="f851f-112">Sekcja *inicjatora*</span><span class="sxs-lookup"><span data-stu-id="f851f-112">The *initializer* section</span></span>

<span data-ttu-id="f851f-113">Instrukcje w sekcji *inicjatora* są wykonywane tylko raz, przed wprowadzeniem pętli.</span><span class="sxs-lookup"><span data-stu-id="f851f-113">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="f851f-114">Sekcja *inicjatora* jest jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f851f-114">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="f851f-115">Deklaracja i inicjalizacja zmiennej pętli lokalnej, do której nie można uzyskać dostępu spoza pętli.</span><span class="sxs-lookup"><span data-stu-id="f851f-115">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="f851f-116">Zero lub więcej wyrażeń instrukcji z następującej listy oddzielonych przecinkami:</span><span class="sxs-lookup"><span data-stu-id="f851f-116">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="f851f-117">instrukcja [przypisania](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-117">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="f851f-118">wywołanie metody</span><span class="sxs-lookup"><span data-stu-id="f851f-118">invocation of a method</span></span>

  - <span data-ttu-id="f851f-119">wyrażenie [przyrostu](../operators/arithmetic-operators.md#increment-operator-) prefiksu lub przyrostkowego, takie jak `++i` lub `i++`</span><span class="sxs-lookup"><span data-stu-id="f851f-119">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="f851f-120">wyrażenie lub [zmniejszanie](../operators/arithmetic-operators.md#decrement-operator---) przyrostowe, takie jak `--i` lub `i--`</span><span class="sxs-lookup"><span data-stu-id="f851f-120">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="f851f-121">Tworzenie obiektu za pomocą operatora [New](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-121">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="f851f-122">wyrażenie [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-122">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="f851f-123">Sekcja *inicjatora* w powyższym przykładzie deklaruje i inicjuje zmienną pętli lokalnej `i` :</span><span class="sxs-lookup"><span data-stu-id="f851f-123">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="f851f-124">Sekcja *warunku*</span><span class="sxs-lookup"><span data-stu-id="f851f-124">The *condition* section</span></span>

<span data-ttu-id="f851f-125">Sekcja *warunku* , jeśli jest obecna, musi być wyrażeniem logicznym.</span><span class="sxs-lookup"><span data-stu-id="f851f-125">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="f851f-126">To wyrażenie jest oceniane przed każdą iteracją pętli.</span><span class="sxs-lookup"><span data-stu-id="f851f-126">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="f851f-127">Jeśli sekcja *Condition* nie istnieje lub wyrażenie logiczne zwraca wartość `true` , wykonywana jest iteracja następnej pętli. w przeciwnym razie pętla zostanie zakończona.</span><span class="sxs-lookup"><span data-stu-id="f851f-127">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="f851f-128">Sekcja *warunek* w powyższym przykładzie określa, czy pętla kończy się na podstawie wartości zmiennej pętli lokalnej:</span><span class="sxs-lookup"><span data-stu-id="f851f-128">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="f851f-129">Sekcja *iteratora*</span><span class="sxs-lookup"><span data-stu-id="f851f-129">The *iterator* section</span></span>

<span data-ttu-id="f851f-130">Sekcja *iterator* definiuje, co się stanie po każdej iteracji treści pętli.</span><span class="sxs-lookup"><span data-stu-id="f851f-130">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="f851f-131">Sekcja *iteratora* zawiera zero lub więcej następujących wyrażeń instrukcji, rozdzielonych przecinkami:</span><span class="sxs-lookup"><span data-stu-id="f851f-131">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="f851f-132">instrukcja [przypisania](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-132">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="f851f-133">wywołanie metody</span><span class="sxs-lookup"><span data-stu-id="f851f-133">invocation of a method</span></span>

- <span data-ttu-id="f851f-134">wyrażenie [przyrostu](../operators/arithmetic-operators.md#increment-operator-) prefiksu lub przyrostkowego, takie jak `++i` lub `i++`</span><span class="sxs-lookup"><span data-stu-id="f851f-134">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="f851f-135">wyrażenie lub [zmniejszanie](../operators/arithmetic-operators.md#decrement-operator---) przyrostowe, takie jak `--i` lub `i--`</span><span class="sxs-lookup"><span data-stu-id="f851f-135">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="f851f-136">Tworzenie obiektu za pomocą operatora [New](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-136">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="f851f-137">wyrażenie [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="f851f-137">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="f851f-138">Sekcja *iterator* w powyższym przykładzie zwiększa zmienną pętli lokalnej:</span><span class="sxs-lookup"><span data-stu-id="f851f-138">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="f851f-139">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f851f-139">Examples</span></span>

<span data-ttu-id="f851f-140">Poniższy przykład ilustruje kilka rzadziej używanych części `for` instrukcji: Przypisywanie wartości do zmiennej pętli zewnętrznej w sekcji *inicjatora* , wywoływanie metody w *inicjatorze* i w sekcjach *iterator* i zmiana wartości dwóch zmiennych w sekcji *iteratora* .</span><span class="sxs-lookup"><span data-stu-id="f851f-140">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="f851f-141">Wybierz pozycję **Uruchom** , aby uruchomić przykładowy kod.</span><span class="sxs-lookup"><span data-stu-id="f851f-141">Select **Run** to run the example code.</span></span> <span data-ttu-id="f851f-142">Następnie można zmodyfikować kod i uruchomić go ponownie.</span><span class="sxs-lookup"><span data-stu-id="f851f-142">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](snippets/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="f851f-143">W poniższym przykładzie zdefiniowano `for` pętlę nieskończoną:</span><span class="sxs-lookup"><span data-stu-id="f851f-143">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](snippets/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="f851f-144">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="f851f-144">C# language specification</span></span>

<span data-ttu-id="f851f-145">Aby uzyskać więcej informacji, zobacz sekcję [dotyczącą instrukcji](~/_csharplang/spec/statements.md#the-for-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="f851f-145">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="f851f-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f851f-146">See also</span></span>

- [<span data-ttu-id="f851f-147">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="f851f-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f851f-148">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="f851f-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f851f-149">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="f851f-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f851f-150">foreach, in</span><span class="sxs-lookup"><span data-stu-id="f851f-150">foreach, in</span></span>](foreach-in.md)
