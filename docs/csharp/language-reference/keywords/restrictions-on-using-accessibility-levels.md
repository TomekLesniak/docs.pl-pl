---
description: Ograniczenia dotyczące używania poziomów ułatwień dostępu — Dokumentacja języka C#
title: Ograniczenia dotyczące używania poziomów ułatwień dostępu — Dokumentacja języka C#
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137004"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="0963e-103">Ograniczenia dotyczące używania poziomów ułatwień dostępu (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0963e-103">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="0963e-104">Po określeniu typu w deklaracji Sprawdź, czy poziom dostępności tego typu jest zależny od poziomu dostępności elementu członkowskiego lub innego typu.</span><span class="sxs-lookup"><span data-stu-id="0963e-104">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="0963e-105">Na przykład bezpośrednia klasa bazowa musi być co najmniej równa dostępności jako Klasa pochodna.</span><span class="sxs-lookup"><span data-stu-id="0963e-105">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="0963e-106">Następujące deklaracje powodują wystąpienie błędu kompilatora, ponieważ klasa bazowa `BaseClass` jest mniej dostępna niż `MyClass` :</span><span class="sxs-lookup"><span data-stu-id="0963e-106">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="0963e-107">Poniższa tabela zawiera podsumowanie ograniczeń dotyczących deklarowanych poziomów dostępności.</span><span class="sxs-lookup"><span data-stu-id="0963e-107">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="0963e-108">Kontekst</span><span class="sxs-lookup"><span data-stu-id="0963e-108">Context</span></span>|<span data-ttu-id="0963e-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0963e-109">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="0963e-110">Klasy</span><span class="sxs-lookup"><span data-stu-id="0963e-110">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="0963e-111">Bezpośrednia klasa bazowa typu klasy musi być co najmniej równa dostępności jako samego typu klasy.</span><span class="sxs-lookup"><span data-stu-id="0963e-111">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="0963e-112">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="0963e-112">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="0963e-113">Jawne interfejsy podstawowe typu interfejsu muszą być co najmniej takie same jak typ interfejsu.</span><span class="sxs-lookup"><span data-stu-id="0963e-113">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="0963e-114">Delegaci</span><span class="sxs-lookup"><span data-stu-id="0963e-114">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="0963e-115">Typ zwracany i typy parametrów typu delegata muszą być co najmniej tak samo jak typ delegata.</span><span class="sxs-lookup"><span data-stu-id="0963e-115">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="0963e-116">Stałe</span><span class="sxs-lookup"><span data-stu-id="0963e-116">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="0963e-117">Typ stałej musi być co najmniej tak samo jak jako stała.</span><span class="sxs-lookup"><span data-stu-id="0963e-117">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="0963e-118">Pola</span><span class="sxs-lookup"><span data-stu-id="0963e-118">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="0963e-119">Typ pola musi być co najmniej tak samo jak w przypadku samego pola.</span><span class="sxs-lookup"><span data-stu-id="0963e-119">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="0963e-120">Metody</span><span class="sxs-lookup"><span data-stu-id="0963e-120">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="0963e-121">Typ zwracany i typy parametrów metody muszą być co najmniej tak samo samo jak metoda.</span><span class="sxs-lookup"><span data-stu-id="0963e-121">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="0963e-122">Właściwości</span><span class="sxs-lookup"><span data-stu-id="0963e-122">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="0963e-123">Typ właściwości musi być co najmniej taki sam jak wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="0963e-123">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="0963e-124">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="0963e-124">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="0963e-125">Typ zdarzenia musi być co najmniej tak samo jak w przypadku samego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0963e-125">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="0963e-126">Indeksatory</span><span class="sxs-lookup"><span data-stu-id="0963e-126">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="0963e-127">Typ i typy parametrów indeksatora muszą być co najmniej tak samo dostępne jak indeksator.</span><span class="sxs-lookup"><span data-stu-id="0963e-127">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="0963e-128">Operatory</span><span class="sxs-lookup"><span data-stu-id="0963e-128">Operators</span></span>](../operators/index.md)|<span data-ttu-id="0963e-129">Typ zwracany i typy parametrów operatora muszą być co najmniej takie same jak dla samego operatora.</span><span class="sxs-lookup"><span data-stu-id="0963e-129">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="0963e-130">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="0963e-130">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="0963e-131">Typy parametrów konstruktora muszą być co najmniej tak samo samo jak Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0963e-131">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="0963e-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="0963e-132">Example</span></span>

<span data-ttu-id="0963e-133">Poniższy przykład zawiera błędne deklaracje różnych typów.</span><span class="sxs-lookup"><span data-stu-id="0963e-133">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="0963e-134">Komentarz po każdej deklaracji wskazuje oczekiwany błąd kompilatora.</span><span class="sxs-lookup"><span data-stu-id="0963e-134">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="0963e-135">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0963e-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0963e-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0963e-136">See also</span></span>

- [<span data-ttu-id="0963e-137">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="0963e-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0963e-138">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="0963e-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0963e-139">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="0963e-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0963e-140">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="0963e-140">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="0963e-141">Domena ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="0963e-141">Accessibility Domain</span></span>](accessibility-domain.md)
- [<span data-ttu-id="0963e-142">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="0963e-142">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="0963e-143">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="0963e-143">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="0963e-144">public</span><span class="sxs-lookup"><span data-stu-id="0963e-144">public</span></span>](public.md)
- [<span data-ttu-id="0963e-145">private</span><span class="sxs-lookup"><span data-stu-id="0963e-145">private</span></span>](private.md)
- [<span data-ttu-id="0963e-146">protected</span><span class="sxs-lookup"><span data-stu-id="0963e-146">protected</span></span>](protected.md)
- [<span data-ttu-id="0963e-147">internal</span><span class="sxs-lookup"><span data-stu-id="0963e-147">internal</span></span>](internal.md)
