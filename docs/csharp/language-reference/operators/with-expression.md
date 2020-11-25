---
title: with Expression-C# — odwołanie
description: Dowiedz się więcej na temat wyrażenia with, które wykonuje nieniszczącą mutację rekordów C#
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: d7d3758c8c5da7859974b5b50b63d2a5ca16b24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702228"
---
# <a name="with-expression-c-reference"></a><span data-ttu-id="304d1-103">with — wyrażenie (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="304d1-103">with expression (C# reference)</span></span>

<span data-ttu-id="304d1-104">W języku C# 9,0 i nowszych, `with` wyrażenie tworzy kopię operandu [rekordu](../../whats-new/csharp-9.md#record-types) z określonymi właściwościami i polami zmodyfikowanymi:</span><span class="sxs-lookup"><span data-stu-id="304d1-104">Available in C# 9.0 and later, a `with` expression produces a copy of its [record](../../whats-new/csharp-9.md#record-types) operand with the specified properties and fields modified:</span></span>

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

<span data-ttu-id="304d1-105">Jak pokazano w powyższym przykładzie, użyj składni [inicjatora obiektów](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) , aby określić, które elementy członkowskie modyfikować i ich nowe wartości.</span><span class="sxs-lookup"><span data-stu-id="304d1-105">As the preceding example shows, you use [object initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) syntax to specify what members to modify and their new values.</span></span> <span data-ttu-id="304d1-106">W `with` wyrażeniu argument operacji po lewej stronie musi być typem rekordu.</span><span class="sxs-lookup"><span data-stu-id="304d1-106">In a `with` expression, a left-hand operand must be of a record type.</span></span>

<span data-ttu-id="304d1-107">Wynik `with` wyrażenia ma ten sam typ środowiska uruchomieniowego co operand wyrażenia, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="304d1-107">The result of a `with` expression has the same runtime type as the expression's operand, as the following example shows:</span></span>

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

<span data-ttu-id="304d1-108">W przypadku elementu członkowskiego typu odwołania tylko odwołanie do wystąpienia jest kopiowane, gdy rekord jest kopiowany.</span><span class="sxs-lookup"><span data-stu-id="304d1-108">In the case of a reference-type member, only the reference to an instance is copied when a record is copied.</span></span> <span data-ttu-id="304d1-109">Zarówno kopia, jak i rekord oryginalny mają dostęp do tego samego wystąpienia typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="304d1-109">Both the copy and original record have access to the same reference-type instance.</span></span> <span data-ttu-id="304d1-110">Poniższy przykład ilustruje takie zachowanie:</span><span class="sxs-lookup"><span data-stu-id="304d1-110">The following example demonstrates that behavior:</span></span>

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

<span data-ttu-id="304d1-111">Każdy typ rekordu ma *Konstruktor kopiujący*.</span><span class="sxs-lookup"><span data-stu-id="304d1-111">Any record type has the *copy constructor*.</span></span> <span data-ttu-id="304d1-112">Jest to Konstruktor z pojedynczym parametrem typu rekordu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="304d1-112">That is a constructor with a single parameter of the containing record type.</span></span> <span data-ttu-id="304d1-113">Kopiuje stan jego argumentu do nowego wystąpienia rekordu.</span><span class="sxs-lookup"><span data-stu-id="304d1-113">It copies the state of its argument to a new record instance.</span></span> <span data-ttu-id="304d1-114">Podczas obliczania `with` wyrażenia Konstruktor kopiujący jest wywoływany w celu utworzenia wystąpienia nowego rekordu na podstawie oryginalnego rekordu.</span><span class="sxs-lookup"><span data-stu-id="304d1-114">At evaluation of a `with` expression, the copy constructor gets called to instantiate a new record instance based on an original record.</span></span> <span data-ttu-id="304d1-115">Następnie nowe wystąpienie zostanie zaktualizowane zgodnie z określonymi modyfikacjami.</span><span class="sxs-lookup"><span data-stu-id="304d1-115">After that, the new instance gets updated according to the specified modifications.</span></span> <span data-ttu-id="304d1-116">Domyślnie Konstruktor kopiujący jest niejawny, czyli wygenerowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="304d1-116">By default, the copy constructor is implicit, that is, compiler-generated.</span></span> <span data-ttu-id="304d1-117">Jeśli musisz dostosować semantykę kopiowania rekordów, jawnie Zadeklaruj konstruktor kopiujący z żądanym zachowaniem.</span><span class="sxs-lookup"><span data-stu-id="304d1-117">If you need to customize the record copy semantics, explicitly declare a copy constructor with the desired behavior.</span></span> <span data-ttu-id="304d1-118">Poniższy przykład aktualizuje poprzedni przykład z jawnym konstruktorem kopiującym.</span><span class="sxs-lookup"><span data-stu-id="304d1-118">The following example updates the preceding example with an explicit copy constructor.</span></span> <span data-ttu-id="304d1-119">Nowe zachowanie kopiowania polega na skopiowaniu elementów listy zamiast odwołania do listy podczas kopiowania rekordu:</span><span class="sxs-lookup"><span data-stu-id="304d1-119">The new copy behavior is to copy list items instead of a list reference when a record is copied:</span></span>

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a><span data-ttu-id="304d1-120">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="304d1-120">C# language specification</span></span>

<span data-ttu-id="304d1-121">Aby uzyskać więcej informacji, zobacz następujące sekcje dotyczące [oferty funkcji Records](~/_csharplang/proposals/csharp-9.0/records.md):</span><span class="sxs-lookup"><span data-stu-id="304d1-121">For more information, see the following sections of the [records feature proposal note](~/_csharplang/proposals/csharp-9.0/records.md):</span></span>

- [<span data-ttu-id="304d1-122">`with` wyrażenia</span><span class="sxs-lookup"><span data-stu-id="304d1-122">`with` expression</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [<span data-ttu-id="304d1-123">Kopiowanie i klonowanie elementów członkowskich</span><span class="sxs-lookup"><span data-stu-id="304d1-123">Copy and Clone members</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a><span data-ttu-id="304d1-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="304d1-124">See also</span></span>

- [<span data-ttu-id="304d1-125">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="304d1-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="304d1-126">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="304d1-126">C# operators and expressions</span></span>](index.md)
