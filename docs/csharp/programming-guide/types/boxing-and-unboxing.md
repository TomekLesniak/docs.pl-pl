---
title: Pakowanie i rozpakowywanie — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat pakowania i rozpakowywania w programowaniu języka C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 5a5bfcc79de8ba3ff66ca8aab9d86d69d89f9221
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380699"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="ed1cc-104">Konwersja boxing i konwersja unboxing (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ed1cc-104">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="ed1cc-105">Opakowanie to proces konwersji [typu wartości](../../language-reference/builtin-types/value-types.md) na typ `object` lub dowolny typ interfejsu implementowany przez ten typ wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-105">Boxing is the process of converting a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="ed1cc-106">Gdy typ wartości pola środowiska uruchomieniowego języka wspólnego (CLR), zawija on wartość wewnątrz <xref:System.Object?displayProperty=nameWithType> wystąpienia i zapisuje je na stosie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-106">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="ed1cc-107">Rozpakowywanie wyodrębnia typ wartości z obiektu.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-107">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="ed1cc-108">Opakowanie jest niejawne; Rozpakowywanie jest jawne.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-108">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="ed1cc-109">Pojęcie opakowania i rozpakowywanie opiera się na ujednoliconym widoku języka C# w systemie typów, w którym wartość dowolnego typu może być traktowana jako obiekt.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-109">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="ed1cc-110">W poniższym przykładzie zmienna Integer `i` jest *opakowana* i przypisana do obiektu `o` .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-110">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="ed1cc-111">Obiekt `o` może być następnie nieopakowany i przypisany do zmiennej całkowitej `i` :</span><span class="sxs-lookup"><span data-stu-id="ed1cc-111">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="ed1cc-112">W poniższych przykładach pokazano, jak opakowanie jest używane w języku C#.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-112">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="ed1cc-113">Wydajność</span><span class="sxs-lookup"><span data-stu-id="ed1cc-113">Performance</span></span>

<span data-ttu-id="ed1cc-114">W odniesieniu do prostych przydziałów, opakowanie i rozpakowywanie są w sposób obliczeniowy kosztowny.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-114">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="ed1cc-115">Gdy typ wartości jest opakowany, nowy obiekt musi być przydzielony i skonstruowany.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-115">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="ed1cc-116">W mniejszym stopniu rzutowanie wymagane do rozpakowywania jest również kosztowne w praktyce.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-116">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="ed1cc-117">Aby uzyskać więcej informacji, zobacz [wydajność](../../../framework/performance/performance-tips.md).</span><span class="sxs-lookup"><span data-stu-id="ed1cc-117">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="ed1cc-118">Boxing</span><span class="sxs-lookup"><span data-stu-id="ed1cc-118">Boxing</span></span>

<span data-ttu-id="ed1cc-119">Opakowanie jest używane do przechowywania typów wartości w stosie zebranych elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-119">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="ed1cc-120">Opakowanie jest niejawną konwersją [typu wartości](../../language-reference/builtin-types/value-types.md) na typ `object` lub dowolny typ interfejsu implementowany przez ten typ wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-120">Boxing is an implicit conversion of a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="ed1cc-121">Opakowanie typu wartości przydziela wystąpienie obiektu na stercie i kopiuje wartość do nowego obiektu.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-121">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="ed1cc-122">Rozważmy następującą deklarację zmiennej typu wartości:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-122">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="ed1cc-123">Poniższa instrukcja niejawnie stosuje operację pakowania na zmiennej `i` :</span><span class="sxs-lookup"><span data-stu-id="ed1cc-123">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="ed1cc-124">Wynikiem tej instrukcji jest utworzenie odwołania do obiektu `o` na stosie, który odwołuje się do wartości typu `int` na stercie.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-124">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="ed1cc-125">Ta wartość jest kopią wartości typu wartości przypisanej do zmiennej `i` .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-125">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="ed1cc-126">Różnica między dwoma zmiennymi, `i` a `o` , jest zilustrowana na poniższej ilustracji konwersji pakującej:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-126">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![Ilustracja przedstawiająca różnicę między zmiennymi i i o.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="ed1cc-128">Istnieje również możliwość, że opakowanie zostało jawnie wykonane, jak w poniższym przykładzie, ale jawne opakowanie nigdy nie jest wymagane:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-128">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="ed1cc-129">Opis</span><span class="sxs-lookup"><span data-stu-id="ed1cc-129">Description</span></span>

<span data-ttu-id="ed1cc-130">Ten przykład konwertuje zmienną całkowitą `i` na obiekt `o` przy użyciu opakowania.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-130">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="ed1cc-131">Następnie wartość przechowywana w zmiennej `i` zostanie zmieniona z `123` na `456` .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-131">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="ed1cc-132">W przykładzie pokazano, że oryginalny typ wartości i obiekt opakowany używają oddzielnych lokalizacji pamięci, w związku z czym można przechowywać różne wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-132">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="ed1cc-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="ed1cc-133">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="ed1cc-134">Rozpakowywanie</span><span class="sxs-lookup"><span data-stu-id="ed1cc-134">Unboxing</span></span>

<span data-ttu-id="ed1cc-135">Rozpakowywanie jest jawną konwersją z typu `object` na [Typ wartości](../../language-reference/builtin-types/value-types.md) lub z typu interfejsu do typu wartości, który implementuje interfejs.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-135">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/builtin-types/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="ed1cc-136">Odpakowywanie operacji składa się z:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-136">An unboxing operation consists of:</span></span>

- <span data-ttu-id="ed1cc-137">Sprawdzanie wystąpienia obiektu, aby upewnić się, że jest to opakowana wartość danego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-137">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="ed1cc-138">Kopiowanie wartości z wystąpienia do zmiennej typu wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-138">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="ed1cc-139">Następujące instrukcje przedstawiają operacje pakowania i rozpakowywania:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-139">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="ed1cc-140">Na poniższej ilustracji przedstawiono wynik poprzednich instrukcji:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-140">The following figure demonstrates the result of the previous statements:</span></span>

![Ilustracja przedstawiająca konwersję rozpakowywanie.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="ed1cc-142">Aby rozpakowywanie typów wartości zakończyło się pomyślnie w czasie wykonywania, element, który jest rozpakowany, musi być odwołaniem do obiektu, który został wcześniej utworzony przez opakowanie wystąpienia tego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-142">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="ed1cc-143">Próba Unbox `null` powoduje <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-143">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="ed1cc-144">Próba Unbox odwołania do niezgodnego typu wartości powoduje wystąpienie <xref:System.InvalidCastException> .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-144">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="ed1cc-145">Przykład</span><span class="sxs-lookup"><span data-stu-id="ed1cc-145">Example</span></span>

<span data-ttu-id="ed1cc-146">Poniższy przykład ilustruje przypadek nieprawidłowego rozpakowywania i wyniki `InvalidCastException` .</span><span class="sxs-lookup"><span data-stu-id="ed1cc-146">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="ed1cc-147">Przy użyciu `try` i `catch` , komunikat o błędzie jest wyświetlany po wystąpieniu błędu.</span><span class="sxs-lookup"><span data-stu-id="ed1cc-147">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="ed1cc-148">Ten program wyprowadza:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-148">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="ed1cc-149">W przypadku zmiany instrukcji:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-149">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="ed1cc-150">na:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-150">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="ed1cc-151">Konwersja zostanie wykonana i otrzymasz dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="ed1cc-151">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="ed1cc-152">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ed1cc-152">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ed1cc-153">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ed1cc-153">See also</span></span>

- [<span data-ttu-id="ed1cc-154">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ed1cc-154">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ed1cc-155">Typy odwołań</span><span class="sxs-lookup"><span data-stu-id="ed1cc-155">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="ed1cc-156">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="ed1cc-156">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
