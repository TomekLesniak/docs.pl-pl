---
description: Class — słowo kluczowe — odwołanie w C#
title: Class — słowo kluczowe — odwołanie w C#
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 67c9c4be55cce25edf9ecb84b257a8523f193bec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142118"
---
# <a name="class-c-reference"></a><span data-ttu-id="2d62f-103">class (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="2d62f-103">class (C# Reference)</span></span>

<span data-ttu-id="2d62f-104">Klasy są deklarowane za pomocą słowa kluczowego `class` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="2d62f-104">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="2d62f-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2d62f-105">Remarks</span></span>

<span data-ttu-id="2d62f-106">W języku C# można używać tylko jednego dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="2d62f-106">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="2d62f-107">Innymi słowy, Klasa może dziedziczyć implementację tylko z jednej klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="2d62f-107">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="2d62f-108">Jednak Klasa może zaimplementować więcej niż jeden interfejs.</span><span class="sxs-lookup"><span data-stu-id="2d62f-108">However, a class can implement more than one interface.</span></span> <span data-ttu-id="2d62f-109">W poniższej tabeli przedstawiono przykłady dziedziczenia klas i implementacji interfejsu:</span><span class="sxs-lookup"><span data-stu-id="2d62f-109">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="2d62f-110">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="2d62f-110">Inheritance</span></span>|<span data-ttu-id="2d62f-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="2d62f-111">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="2d62f-112">Brak</span><span class="sxs-lookup"><span data-stu-id="2d62f-112">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="2d62f-113">Pojedynczy</span><span class="sxs-lookup"><span data-stu-id="2d62f-113">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="2d62f-114">Brak, implementuje dwa interfejsy</span><span class="sxs-lookup"><span data-stu-id="2d62f-114">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="2d62f-115">Single, implementuje jeden interfejs</span><span class="sxs-lookup"><span data-stu-id="2d62f-115">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="2d62f-116">Klasy zadeklarowane bezpośrednio w przestrzeni nazw, a nie zagnieżdżone w innych klasach, mogą być [publiczne](./public.md) lub [wewnętrzne](./internal.md).</span><span class="sxs-lookup"><span data-stu-id="2d62f-116">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="2d62f-117">Klasy są `internal` domyślnie.</span><span class="sxs-lookup"><span data-stu-id="2d62f-117">Classes are `internal` by default.</span></span>

<span data-ttu-id="2d62f-118">Elementy członkowskie klasy, w tym klasy zagnieżdżone, mogą być [publiczne](public.md), [chronione wewnętrznie](protected-internal.md), [chronione](protected.md), [wewnętrzne](internal.md), [prywatne](private.md)i [prywatne](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="2d62f-118">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="2d62f-119">Elementy członkowskie są `private` domyślnie.</span><span class="sxs-lookup"><span data-stu-id="2d62f-119">Members are `private` by default.</span></span>

<span data-ttu-id="2d62f-120">Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="2d62f-120">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="2d62f-121">Można zadeklarować klasy ogólne z parametrami typu.</span><span class="sxs-lookup"><span data-stu-id="2d62f-121">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="2d62f-122">Aby uzyskać więcej informacji, zobacz [klasy ogólne](../../programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2d62f-122">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="2d62f-123">Klasa może zawierać deklaracje następujących elementów członkowskich:</span><span class="sxs-lookup"><span data-stu-id="2d62f-123">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="2d62f-124">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="2d62f-124">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="2d62f-125">Stałe</span><span class="sxs-lookup"><span data-stu-id="2d62f-125">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="2d62f-126">Pola</span><span class="sxs-lookup"><span data-stu-id="2d62f-126">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="2d62f-127">Finalizatory</span><span class="sxs-lookup"><span data-stu-id="2d62f-127">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="2d62f-128">Metody</span><span class="sxs-lookup"><span data-stu-id="2d62f-128">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="2d62f-129">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2d62f-129">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="2d62f-130">Indeksatory</span><span class="sxs-lookup"><span data-stu-id="2d62f-130">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="2d62f-131">Operatory</span><span class="sxs-lookup"><span data-stu-id="2d62f-131">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="2d62f-132">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="2d62f-132">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="2d62f-133">Delegaci</span><span class="sxs-lookup"><span data-stu-id="2d62f-133">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="2d62f-134">Klasy</span><span class="sxs-lookup"><span data-stu-id="2d62f-134">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="2d62f-135">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="2d62f-135">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="2d62f-136">Typy struktur</span><span class="sxs-lookup"><span data-stu-id="2d62f-136">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="2d62f-137">Typów wyliczeniowych</span><span class="sxs-lookup"><span data-stu-id="2d62f-137">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="2d62f-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="2d62f-138">Example</span></span>

<span data-ttu-id="2d62f-139">Poniższy przykład demonstruje deklarowanie pól klasy, konstruktorów i metod.</span><span class="sxs-lookup"><span data-stu-id="2d62f-139">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="2d62f-140">Ilustruje także tworzenie wystąpień obiektów i drukowanie danych wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="2d62f-140">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="2d62f-141">W tym przykładzie zadeklarowane są dwie klasy.</span><span class="sxs-lookup"><span data-stu-id="2d62f-141">In this example, two classes are declared.</span></span> <span data-ttu-id="2d62f-142">Pierwsza klasa, `Child` , zawiera dwa prywatne pola ( `name` i `age` ), dwa konstruktory publiczne i jedną metodę publiczną.</span><span class="sxs-lookup"><span data-stu-id="2d62f-142">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="2d62f-143">Druga klasa, `StringTest` ,,, jest używana do przechowywania `Main` .</span><span class="sxs-lookup"><span data-stu-id="2d62f-143">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="2d62f-144">Komentarze</span><span class="sxs-lookup"><span data-stu-id="2d62f-144">Comments</span></span>

<span data-ttu-id="2d62f-145">Zwróć uwagę, że w poprzednim przykładzie pola prywatne ( `name` i `age` ) można uzyskać dostęp tylko za pomocą metody publicznej `Child` klasy.</span><span class="sxs-lookup"><span data-stu-id="2d62f-145">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="2d62f-146">Na przykład nie można wydrukować nazwy elementu podrzędnego z `Main` metody przy użyciu instrukcji podobnej do następujących:</span><span class="sxs-lookup"><span data-stu-id="2d62f-146">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="2d62f-147">Uzyskiwanie dostępu do prywatnych elementów członkowskich `Child` z programu `Main` byłoby możliwe tylko wtedy `Main` , gdy należały do klasy.</span><span class="sxs-lookup"><span data-stu-id="2d62f-147">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="2d62f-148">Typy zadeklarowane wewnątrz klasy bez modyfikatora dostępu domyślnie do `private` , dlatego elementy członkowskie danych w tym przykładzie nadal byłyby, `private` Jeśli słowo kluczowe zostało usunięte.</span><span class="sxs-lookup"><span data-stu-id="2d62f-148">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="2d62f-149">Na koniec należy zauważyć, że dla obiektu utworzonego przy użyciu konstruktora bez parametrów ( `child3` ) `age` pole zostało domyślnie zainicjowane do zera.</span><span class="sxs-lookup"><span data-stu-id="2d62f-149">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2d62f-150">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="2d62f-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2d62f-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2d62f-151">See also</span></span>

- [<span data-ttu-id="2d62f-152">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="2d62f-152">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2d62f-153">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2d62f-153">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2d62f-154">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="2d62f-154">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="2d62f-155">Typy odwołań</span><span class="sxs-lookup"><span data-stu-id="2d62f-155">Reference Types</span></span>](./reference-types.md)
