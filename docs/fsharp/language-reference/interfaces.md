---
title: Interfejsy
description: 'Dowiedz się, jak interfejsy języka F # określają zestawy powiązanych elementów członkowskich, które są implementowane przez inne klasy.'
ms.date: 08/15/2020
ms.openlocfilehash: 36272b52fcff83e8e8a54ccc4e6ecd1252a91819
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558130"
---
# <a name="interfaces"></a><span data-ttu-id="8a818-103">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="8a818-103">Interfaces</span></span>

<span data-ttu-id="8a818-104">*Interfejsy* określają zestawy powiązanych członków, które są implementowane przez inne klasy.</span><span class="sxs-lookup"><span data-stu-id="8a818-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a818-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8a818-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="8a818-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8a818-106">Remarks</span></span>

<span data-ttu-id="8a818-107">Deklaracje interfejsów przypominają deklaracje klas, z tą różnicą, że żaden element członkowski nie jest zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="8a818-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="8a818-108">Zamiast tego wszystkie elementy członkowskie są abstrakcyjne, zgodnie ze wskazaniem słowa kluczowego `abstract` .</span><span class="sxs-lookup"><span data-stu-id="8a818-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="8a818-109">Nie udostępniamy treści metody dla metod abstrakcyjnych.</span><span class="sxs-lookup"><span data-stu-id="8a818-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="8a818-110">Można jednak podać domyślną implementację, uwzględniając także odrębną definicję elementu członkowskiego jako metodę razem ze `default` słowem kluczowym.</span><span class="sxs-lookup"><span data-stu-id="8a818-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="8a818-111">Jest to równoznaczne z tworzeniem metody wirtualnej w klasie bazowej w innych językach .NET.</span><span class="sxs-lookup"><span data-stu-id="8a818-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="8a818-112">Taka metoda wirtualna może zostać przesłonięta w klasach, które implementują interfejs.</span><span class="sxs-lookup"><span data-stu-id="8a818-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="8a818-113">Domyślnymi ułatwieniami dostępu dla interfejsów są `public` .</span><span class="sxs-lookup"><span data-stu-id="8a818-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="8a818-114">Opcjonalnie możesz nadać każdemu parametrowi metody nazwę przy użyciu standardowej składni F #:</span><span class="sxs-lookup"><span data-stu-id="8a818-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="8a818-115">W powyższym `ISprintable` przykładzie `Print` Metoda ma jeden parametr typu `string` o nazwie `format` .</span><span class="sxs-lookup"><span data-stu-id="8a818-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="8a818-116">Istnieją dwa sposoby implementacji interfejsów: przy użyciu wyrażeń obiektów i typów klas.</span><span class="sxs-lookup"><span data-stu-id="8a818-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="8a818-117">W obu przypadkach typ klasy lub wyrażenie obiektu zawiera treść metody dla abstrakcyjnych metod interfejsu.</span><span class="sxs-lookup"><span data-stu-id="8a818-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="8a818-118">Implementacje są specyficzne dla każdego typu, który implementuje interfejs.</span><span class="sxs-lookup"><span data-stu-id="8a818-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="8a818-119">W związku z tym metody interfejsu dla różnych typów mogą się różnić od siebie.</span><span class="sxs-lookup"><span data-stu-id="8a818-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="8a818-120">Słowa kluczowe `interface` i `end` , które oznaczają początek i koniec definicji, są opcjonalne w przypadku używania lekkiej składni.</span><span class="sxs-lookup"><span data-stu-id="8a818-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="8a818-121">Jeśli nie używasz tych słów kluczowych, kompilator próbuje określić, czy typ jest klasą, czy interfejsem, analizując używane konstrukcje.</span><span class="sxs-lookup"><span data-stu-id="8a818-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="8a818-122">Jeśli zdefiniujesz element członkowski lub użyjesz innej składni klasy, typ jest interpretowany jako Klasa.</span><span class="sxs-lookup"><span data-stu-id="8a818-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="8a818-123">Styl kodowania .NET polega na rozpoczęciu wszystkich interfejsów z stolicą `I` .</span><span class="sxs-lookup"><span data-stu-id="8a818-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

<span data-ttu-id="8a818-124">Można określić wiele parametrów na dwa sposoby: F #-styl i. Styl sieci.</span><span class="sxs-lookup"><span data-stu-id="8a818-124">You can specify multiple parameters in two ways: F#-style and .NET-style.</span></span> <span data-ttu-id="8a818-125">Oba te wersje zostaną skompilowane w taki sam sposób dla użytkowników platformy .NET, ale styl F # spowoduje wymuszenie wywoływania przez program F # aplikacji parametrów języka F # i. Styl sieci spowoduje wymuszenie wywoływania przez program F # wywołań aplikacji argumentu z krotką.</span><span class="sxs-lookup"><span data-stu-id="8a818-125">Both will compile the same way for .NET consumers, but F#-style will force F# callers to use F#-style parameter application and .NET-style will force F# callers to use tupled argument application.</span></span>

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="8a818-126">Implementowanie interfejsów przy użyciu typów klas</span><span class="sxs-lookup"><span data-stu-id="8a818-126">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="8a818-127">Można zaimplementować jeden lub więcej interfejsów w typie klasy za pomocą `interface` słowa kluczowego, nazwy interfejsu i `with` słowa kluczowego, a następnie definicji elementu członkowskiego interfejsu, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8a818-127">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="8a818-128">Implementacje interfejsu są dziedziczone, więc wszystkie klasy pochodne nie muszą ponownie wdrażać.</span><span class="sxs-lookup"><span data-stu-id="8a818-128">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="8a818-129">Wywoływanie metod interfejsu</span><span class="sxs-lookup"><span data-stu-id="8a818-129">Calling Interface Methods</span></span>

<span data-ttu-id="8a818-130">Metody interfejsu można wywoływać tylko za pomocą interfejsu, a nie za pomocą dowolnego obiektu typu, który implementuje interfejs.</span><span class="sxs-lookup"><span data-stu-id="8a818-130">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="8a818-131">W ten sposób może być konieczne przerzutowanie na typ interfejsu za pomocą `:>` operatora lub `upcast` operatora w celu wywołania tych metod.</span><span class="sxs-lookup"><span data-stu-id="8a818-131">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="8a818-132">Aby wywołać metodę interfejsu, gdy masz obiekt typu `SomeClass` , należy przerzutować obiekt na typ interfejsu, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8a818-132">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="8a818-133">Alternatywą jest zadeklarowanie metody na obiekcie, który rzutuje i wywołuje metodę interfejsu, jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8a818-133">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="8a818-134">Implementowanie interfejsów przy użyciu wyrażeń obiektów</span><span class="sxs-lookup"><span data-stu-id="8a818-134">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="8a818-135">Wyrażenia obiektów zapewniają krótki sposób implementacji interfejsu.</span><span class="sxs-lookup"><span data-stu-id="8a818-135">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="8a818-136">Są one przydatne, gdy nie trzeba tworzyć nazwanego typu, a ty chcesz tylko obiekt obsługujący metody interfejsu, bez żadnych dodatkowych metod.</span><span class="sxs-lookup"><span data-stu-id="8a818-136">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="8a818-137">Wyrażenie obiektu jest zilustrowane w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8a818-137">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="8a818-138">Dziedziczenie interfejsu</span><span class="sxs-lookup"><span data-stu-id="8a818-138">Interface Inheritance</span></span>

<span data-ttu-id="8a818-139">Interfejsy mogą dziedziczyć z jednego lub kilku interfejsów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="8a818-139">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="8a818-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8a818-140">See also</span></span>

- [<span data-ttu-id="8a818-141">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="8a818-141">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8a818-142">Wyrażenia obiektów</span><span class="sxs-lookup"><span data-stu-id="8a818-142">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="8a818-143">Klasy</span><span class="sxs-lookup"><span data-stu-id="8a818-143">Classes</span></span>](classes.md)
