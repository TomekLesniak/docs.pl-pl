---
title: Jak używać niejawnie wpisanych zmiennych lokalnych i tablic w wyrażeniu zapytania — Przewodnik programowania w języku C#
description: Użyj niejawnie wpisanych zmiennych lokalnych w języku C#, aby kompilator mógł określić typ zmiennej lokalnej. Musisz użyć ich do przechowywania typów anonimowych.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 0379cf7a172b989a9c686fd2da20ca8bf8da4997
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098868"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="b86a8-104">Jak używać niejawnie wpisanych zmiennych lokalnych i tablic w wyrażeniu zapytania (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b86a8-104">How to use implicitly typed local variables and arrays in a query expression (C# Programming Guide)</span></span>

<span data-ttu-id="b86a8-105">Możesz użyć niejawnie wpisanych zmiennych lokalnych, ilekroć kompilator ma określić typ zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="b86a8-105">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="b86a8-106">Należy użyć niejawnie wpisanych zmiennych lokalnych do przechowywania typów anonimowych, które są często używane w wyrażeniach zapytań.</span><span class="sxs-lookup"><span data-stu-id="b86a8-106">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="b86a8-107">Poniższe przykłady ilustrują opcjonalne i wymagane zastosowania niejawnie wpisanych zmiennych lokalnych w zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="b86a8-107">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="b86a8-108">Niejawnie wpisane zmienne lokalne są deklarowane przy użyciu słowa kluczowego [var](../../language-reference/keywords/var.md) .</span><span class="sxs-lookup"><span data-stu-id="b86a8-108">Implicitly typed local variables are declared by using the [var](../../language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="b86a8-109">Aby uzyskać więcej informacji, zobacz [niejawnie wpisane zmienne lokalne](./implicitly-typed-local-variables.md) i [niejawnie wpisane tablice](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b86a8-109">For more information, see [Implicitly Typed Local Variables](./implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b86a8-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="b86a8-110">Example</span></span>  

 <span data-ttu-id="b86a8-111">W poniższym przykładzie przedstawiono typowy scenariusz, w którym `var` słowo kluczowe jest wymagane: wyrażenie zapytania, które tworzy sekwencję typów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="b86a8-111">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="b86a8-112">W tym scenariuszu zarówno zmienna zapytania, jak i Zmienna iteracji w `foreach` instrukcji muszą zostać wpisane niejawnie przy użyciu, `var` ponieważ nie masz dostępu do nazwy typu dla typu anonimowego.</span><span class="sxs-lookup"><span data-stu-id="b86a8-112">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="b86a8-113">Aby uzyskać więcej informacji na temat typów anonimowych, zobacz [Typy anonimowe](./anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="b86a8-113">For more information about anonymous types, see [Anonymous Types](./anonymous-types.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="b86a8-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="b86a8-114">Example</span></span>  

 <span data-ttu-id="b86a8-115">W poniższym przykładzie użyto `var` słowa kluczowego w podobnej sytuacji, ale w którym użycie `var` jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="b86a8-115">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="b86a8-116">Ponieważ `student.LastName` jest ciągiem, wykonywanie zapytania zwraca sekwencję ciągów.</span><span class="sxs-lookup"><span data-stu-id="b86a8-116">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="b86a8-117">W związku z tym typ `queryID` może być zadeklarowany jako `System.Collections.Generic.IEnumerable<string>` zamiast `var` .</span><span class="sxs-lookup"><span data-stu-id="b86a8-117">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="b86a8-118">Słowo kluczowe `var` jest używane w celu wygody.</span><span class="sxs-lookup"><span data-stu-id="b86a8-118">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="b86a8-119">W przykładzie zmienna iteracji w `foreach` instrukcji jest jawnie wpisana jako ciąg, ale zamiast tego może być zadeklarowana przy użyciu `var` .</span><span class="sxs-lookup"><span data-stu-id="b86a8-119">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="b86a8-120">Ponieważ typ zmiennej iteracji nie jest typem anonimowym, użycie `var` jest opcją, a nie wymaganie.</span><span class="sxs-lookup"><span data-stu-id="b86a8-120">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="b86a8-121">Pamiętaj, `var` że sam nie jest typem, ale instrukcją kompilatora do wnioskowania i przypisania typu.</span><span class="sxs-lookup"><span data-stu-id="b86a8-121">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a><span data-ttu-id="b86a8-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b86a8-122">See also</span></span>

- [<span data-ttu-id="b86a8-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b86a8-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b86a8-124">Metody rozszerzeń</span><span class="sxs-lookup"><span data-stu-id="b86a8-124">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="b86a8-125">LINQ (zapytanie zintegrowane z językiem)</span><span class="sxs-lookup"><span data-stu-id="b86a8-125">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="b86a8-126">var</span><span class="sxs-lookup"><span data-stu-id="b86a8-126">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="b86a8-127">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="b86a8-127">LINQ in C#</span></span>](../../linq/index.md)
