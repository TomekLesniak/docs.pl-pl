---
description: ReadOnly — słowo kluczowe — odwołanie w C#
title: ReadOnly — słowo kluczowe — odwołanie w C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: b1bab5af18216fcef2162179493dbbb59e3470cf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137178"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="1699b-103">readonly (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="1699b-103">readonly (C# Reference)</span></span>

<span data-ttu-id="1699b-104">`readonly`Słowo kluczowe jest modyfikatorem, który może być używany w czterech kontekstach:</span><span class="sxs-lookup"><span data-stu-id="1699b-104">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="1699b-105">W [deklaracji pola](#readonly-field-example)wskazuje, `readonly` że przypisanie do pola może wystąpić tylko jako część deklaracji lub w konstruktorze w tej samej klasie.</span><span class="sxs-lookup"><span data-stu-id="1699b-105">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="1699b-106">Pole tylko do odczytu można przypisać i ponownie przypisać wiele razy w deklaracji pola i konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="1699b-106">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="1699b-107">`readonly`Nie można przypisać pola po zakończeniu konstruktora.</span><span class="sxs-lookup"><span data-stu-id="1699b-107">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="1699b-108">Ta reguła ma inne konsekwencje dla typów wartości i typów referencyjnych:</span><span class="sxs-lookup"><span data-stu-id="1699b-108">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="1699b-109">Ponieważ typy wartości bezpośrednio zawierają swoje dane, pole, które jest  `readonly` typem wartości, jest niezmienne.</span><span class="sxs-lookup"><span data-stu-id="1699b-109">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="1699b-110">Ponieważ typy odwołań zawierają odwołanie do swoich danych, pole, które jest `readonly` typem referencyjnym, musi zawsze odwoływać się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="1699b-110">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="1699b-111">Ten obiekt nie jest niezmienny.</span><span class="sxs-lookup"><span data-stu-id="1699b-111">That object isn't immutable.</span></span> <span data-ttu-id="1699b-112">`readonly`Modyfikator zapobiega zastąpieniu pola przez inne wystąpienie typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="1699b-112">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="1699b-113">Jednak modyfikator nie zapobiega modyfikowaniu danych wystąpienia pola za pośrednictwem pola tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="1699b-113">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="1699b-114">Typ widoczny na zewnątrz, który zawiera zewnętrzny widoczny pole tylko do odczytu, które jest modyfikowalnym typem odwołania może być luką w zabezpieczeniach i może wyzwolić ostrzeżenie [CA2104](/visualstudio/code-quality/ca2104) : "nie deklaruj tylko odczytu modyfikowalnych typów odwołań".</span><span class="sxs-lookup"><span data-stu-id="1699b-114">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="1699b-115">W `readonly struct` definicji typu wskazuje, `readonly` że typ struktury jest niezmienny.</span><span class="sxs-lookup"><span data-stu-id="1699b-115">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="1699b-116">Aby uzyskać więcej informacji, zobacz sekcję [ `readonly` struktury](../builtin-types/struct.md#readonly-struct) w artykule [typy struktury](../builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="1699b-116">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1699b-117">W deklaracji elementu członkowskiego wystąpienia w typie struktury `readonly` wskazuje, że element członkowski wystąpienia nie modyfikuje stanu struktury.</span><span class="sxs-lookup"><span data-stu-id="1699b-117">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="1699b-118">Aby uzyskać więcej informacji, zobacz sekcję [ `readonly` elementy członkowskie wystąpienia](../builtin-types/struct.md#readonly-instance-members) w artykule [typy struktury](../builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="1699b-118">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1699b-119">W [ `ref readonly` zwracanej metodzie](#ref-readonly-return-example) `readonly` modyfikator wskazuje, że metoda zwraca odwołanie, a zapisy nie są dozwolone dla tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="1699b-119">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="1699b-120">`readonly struct` `ref readonly` Konteksty i zostały dodane w języku C# 7,2.</span><span class="sxs-lookup"><span data-stu-id="1699b-120">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="1699b-121">`readonly` elementy członkowskie struktury zostały dodane w języku C# 8,0</span><span class="sxs-lookup"><span data-stu-id="1699b-121">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="1699b-122">Przykład pola tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="1699b-122">Readonly field example</span></span>

<span data-ttu-id="1699b-123">W tym przykładzie wartość pola `year` nie może zostać zmieniona w metodzie `ChangeYear` , mimo że jest przypisana wartość w konstruktorze klasy:</span><span class="sxs-lookup"><span data-stu-id="1699b-123">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="1699b-124">Można przypisać wartość do `readonly` pola tylko w następujących kontekstach:</span><span class="sxs-lookup"><span data-stu-id="1699b-124">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="1699b-125">Gdy zmienna jest inicjowana w deklaracji, na przykład:</span><span class="sxs-lookup"><span data-stu-id="1699b-125">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="1699b-126">W konstruktorze wystąpienia klasy, która zawiera deklarację pola wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1699b-126">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="1699b-127">W konstruktorze statycznym klasy, która zawiera deklarację pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="1699b-127">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="1699b-128">Te konteksty konstruktorów są również jedynymi kontekstami, w których są prawidłowe w celu przekazania `readonly` pola jako parametru [out](out-parameter-modifier.md) lub [ref](ref.md) .</span><span class="sxs-lookup"><span data-stu-id="1699b-128">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="1699b-129">`readonly`Słowo kluczowe różni się od słowa kluczowego [const](const.md) .</span><span class="sxs-lookup"><span data-stu-id="1699b-129">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="1699b-130">`const`Pole może być inicjowane tylko w deklaracji pola.</span><span class="sxs-lookup"><span data-stu-id="1699b-130">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="1699b-131">`readonly`Pole można przypisać wiele razy w deklaracji pola i w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="1699b-131">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="1699b-132">W związku z tym `readonly` pola mogą mieć różne wartości w zależności od użytego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="1699b-132">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="1699b-133">Ponadto, gdy `const` pole jest stałą czasu kompilacji, `readonly` pole może być używane dla stałych czasu wykonywania, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="1699b-133">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="1699b-134">W poprzednim przykładzie, jeśli używasz instrukcji podobnej do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="1699b-134">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="1699b-135">zostanie wyświetlony komunikat o błędzie kompilatora:</span><span class="sxs-lookup"><span data-stu-id="1699b-135">you'll get the compiler error message:</span></span>

<span data-ttu-id="1699b-136">**Nie można przypisać do pola tylko do odczytu (z wyjątkiem w konstruktorze lub inicjatorze zmiennych).**</span><span class="sxs-lookup"><span data-stu-id="1699b-136">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="1699b-137">Przykład powrotu ref ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1699b-137">Ref readonly return example</span></span>

<span data-ttu-id="1699b-138">`readonly`Modyfikator na `ref return` wskazuje, że zwracane odwołanie nie może być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="1699b-138">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="1699b-139">Poniższy przykład zwraca odwołanie do źródła.</span><span class="sxs-lookup"><span data-stu-id="1699b-139">The following example returns a reference to the origin.</span></span> <span data-ttu-id="1699b-140">Używa `readonly` modyfikatora, aby wskazać, że obiekty wywołujące nie mogą modyfikować pochodzenia:</span><span class="sxs-lookup"><span data-stu-id="1699b-140">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="1699b-141">Zwracany typ nie musi być `readonly struct` .</span><span class="sxs-lookup"><span data-stu-id="1699b-141">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="1699b-142">Każdy typ, który może być zwracany przez, `ref` może być zwracany przez `ref readonly` .</span><span class="sxs-lookup"><span data-stu-id="1699b-142">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1699b-143">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="1699b-143">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="1699b-144">Możesz również zobaczyć propozycje specyfikacji języka:</span><span class="sxs-lookup"><span data-stu-id="1699b-144">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="1699b-145">Typ ref i tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="1699b-145">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="1699b-146">elementy członkowskie struktury tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="1699b-146">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="1699b-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1699b-147">See also</span></span>

- [<span data-ttu-id="1699b-148">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="1699b-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1699b-149">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="1699b-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1699b-150">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="1699b-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1699b-151">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="1699b-151">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1699b-152">const</span><span class="sxs-lookup"><span data-stu-id="1699b-152">const</span></span>](const.md)
- [<span data-ttu-id="1699b-153">Pola</span><span class="sxs-lookup"><span data-stu-id="1699b-153">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
