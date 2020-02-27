---
title: Typy struktury — C# odwołanie
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6113912f176d2d7b68c77ff2e78a361b373ca31a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634870"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="1ff7f-102">Typy struktur (C# odwołanie)</span><span class="sxs-lookup"><span data-stu-id="1ff7f-102">Structure types (C# reference)</span></span>

<span data-ttu-id="1ff7f-103">*Typ struktury* (lub *Typ struktury*) jest [typem wartości](value-types.md) , który może hermetyzować dane i powiązane funkcje.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-103">A *structure type* (or *struct type*) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="1ff7f-104">Za pomocą słowa kluczowego `struct` można zdefiniować typ struktury:</span><span class="sxs-lookup"><span data-stu-id="1ff7f-104">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](~/samples/csharp/language-reference/builtin-types/StructType.cs#StructExample)]

<span data-ttu-id="1ff7f-105">Typy struktury mają *semantykę wartości*.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-105">Structure types have *value semantics*.</span></span> <span data-ttu-id="1ff7f-106">Oznacza to, że zmienna typu struktury zawiera wystąpienie typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-106">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="1ff7f-107">Domyślnie wartości zmiennych są kopiowane przy przypisywaniu, przekazywanie argumentu do metody i zwracanie wyniku metody.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-107">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="1ff7f-108">W przypadku zmiennej typu struktury jest kopiowane wystąpienie typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-108">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="1ff7f-109">Aby uzyskać więcej informacji, zobacz [typy wartości](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-109">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="1ff7f-110">Zwykle typy struktury umożliwiają projektowanie małych typów skoncentrowanych na danych, które zapewniają niewielki lub nie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-110">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="1ff7f-111">Na przykład program .NET używa typów struktury do reprezentowania liczby (zarówno [liczby całkowitej](integral-numeric-types.md) , jak i [rzeczywistej](floating-point-numeric-types.md)), [wartości logicznej](bool.md), [znaku Unicode](char.md)i [wystąpienia czasu](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-111">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="1ff7f-112">Jeśli planujesz zachowanie typu, rozważ zdefiniowanie [klasy](../keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-112">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="1ff7f-113">Typy klas mają *semantykę odwołań*.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-113">Class types have *reference semantics*.</span></span> <span data-ttu-id="1ff7f-114">Oznacza to, że zmienna typu klasy zawiera odwołanie do wystąpienia typu, a nie samego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-114">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="1ff7f-115">Ograniczenia dotyczące projektowania typu struktury</span><span class="sxs-lookup"><span data-stu-id="1ff7f-115">Limitations with the design of a structure type</span></span>

<span data-ttu-id="1ff7f-116">Podczas projektowania typu struktury można korzystać z takich samych możliwości jak w przypadku typu [klasy](../keywords/class.md) , z następującymi wyjątkami:</span><span class="sxs-lookup"><span data-stu-id="1ff7f-116">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="1ff7f-117">Nie można zadeklarować konstruktora bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-117">You cannot declare a parameterless constructor.</span></span> <span data-ttu-id="1ff7f-118">Każdy typ struktury zawiera już niejawny Konstruktor bez parametrów, który generuje [wartość domyślną](default-values.md) typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-118">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="1ff7f-119">Nie można zainicjować pola wystąpienia lub właściwości w swojej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-119">You cannot initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="1ff7f-120">Można jednak zainicjować pole [static](../keywords/static.md) lub [const](../keywords/const.md) lub właściwość statyczną w swojej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-120">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="1ff7f-121">Konstruktor typu struktury musi inicjować wszystkie pola wystąpienia typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-121">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="1ff7f-122">Typ struktury nie może dziedziczyć z innego typu klasy lub struktury i nie może być podstawą klasy.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-122">A structure type cannot inherit from other class or structure type and it cannot be the base of a class.</span></span> <span data-ttu-id="1ff7f-123">Jednak typ struktury może implementować [interfejsy](../keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-123">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="1ff7f-124">Nie można zadeklarować [finalizatora](../../programming-guide/classes-and-structs/destructors.md) w obrębie typu struktury.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-124">You cannot declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="1ff7f-125">Tworzenie wystąpienia typu struktury</span><span class="sxs-lookup"><span data-stu-id="1ff7f-125">Instantiation of a structure type</span></span>

<span data-ttu-id="1ff7f-126">W C#, musisz zainicjować zadeklarowaną zmienną, zanim będzie można jej użyć.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-126">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="1ff7f-127">Ponieważ zmienna typu struktury nie może być `null` (chyba że jest to zmienna [typu wartości null](nullable-value-types.md)), należy utworzyć wystąpienie odpowiedniego typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-127">Because a structure-type variable cannot be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="1ff7f-128">Istnieje kilka sposobów, aby to zrobić.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-128">There are several ways to do that.</span></span>

<span data-ttu-id="1ff7f-129">Zazwyczaj tworzysz typ struktury, wywołując odpowiedni Konstruktor z operatorem [`new`](../operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="1ff7f-129">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="1ff7f-130">Każdy typ struktury ma co najmniej jednego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-130">Every structure type has at least one constructor.</span></span> <span data-ttu-id="1ff7f-131">Jest to niejawny Konstruktor bez parametrów, który tworzy [wartość domyślną](default-values.md) typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-131">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="1ff7f-132">Można również użyć operatora [domyślnego](../operators/default.md) lub literału, aby utworzyć wartość domyślną typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-132">You can also use the [default](../operators/default.md) operator or literal to produce the default value of a type.</span></span>

<span data-ttu-id="1ff7f-133">Jeśli wszystkie pola wystąpienia typu struktury są dostępne, można również utworzyć ich wystąpienie bez operatora `new`.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-133">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="1ff7f-134">W takim przypadku należy zainicjować wszystkie pola wystąpienia przed pierwszym użyciem wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-134">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="1ff7f-135">Poniższy przykład pokazuje, jak to zrobić:</span><span class="sxs-lookup"><span data-stu-id="1ff7f-135">The following example shows how to do that:</span></span>

[!code-csharp[without new](~/samples/csharp/language-reference/builtin-types/StructType.cs#WithoutNew)]

<span data-ttu-id="1ff7f-136">W przypadku [wbudowanych typów wartości](value-types.md#built-in-value-types)Użyj odpowiednich literałów, aby określić wartość typu.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-136">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="1ff7f-137">Przekazywanie zmiennych typu struktury przez odwołanie</span><span class="sxs-lookup"><span data-stu-id="1ff7f-137">Passing structure-type variables by reference</span></span>

<span data-ttu-id="1ff7f-138">W przypadku przekazania zmiennej typu struktury do metody jako argumentu lub zwrócenia wartości typu struktury z metody, kopiowane jest całe wystąpienie typu struktury.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-138">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="1ff7f-139">To może mieć wpływ na wydajność kodu w scenariuszach o wysokiej wydajności, które obejmują duże typy struktury.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-139">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="1ff7f-140">Można uniknąć kopiowania wartości przez przekazanie zmiennej typu struktury przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-140">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="1ff7f-141">Użyj modyfikatorów parametrów [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md)lub [`in`](../keywords/in-parameter-modifier.md) , aby wskazać, że argument musi być przekazaniem przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-141">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="1ff7f-142">Użyj funkcji [ref](../../programming-guide/classes-and-structs/ref-returns.md) Returns, aby zwrócić wynik metody przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-142">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="1ff7f-143">Aby uzyskać więcej informacji, zobacz [Zapisywanie bezpiecznego i C# wydajnego kodu](../../write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-143">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="1ff7f-144">Konwersje</span><span class="sxs-lookup"><span data-stu-id="1ff7f-144">Conversions</span></span>

<span data-ttu-id="1ff7f-145">Dla dowolnego typu struktury istnieje konwersja [opakowania i rozpakowywanie](../../programming-guide/types/boxing-and-unboxing.md) do i z typów <xref:System.ValueType?displayProperty=nameWithType> i <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-145">For any structure type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="1ff7f-146">Istnieje również możliwość pakowania i rozpakowywania konwersji między typem struktury i dowolnym interfejsem, który implementuje.</span><span class="sxs-lookup"><span data-stu-id="1ff7f-146">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1ff7f-147">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="1ff7f-147">C# language specification</span></span>

<span data-ttu-id="1ff7f-148">Aby uzyskać więcej informacji, zobacz sekcję [struktury](~/_csharplang/spec/structs.md) w [ C# specyfikacji języka](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1ff7f-148">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ff7f-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ff7f-149">See also</span></span>

- [<span data-ttu-id="1ff7f-150">C#odwoła</span><span class="sxs-lookup"><span data-stu-id="1ff7f-150">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1ff7f-151">Wytyczne dotyczące projektowania — wybór między klasą a strukturą</span><span class="sxs-lookup"><span data-stu-id="1ff7f-151">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="1ff7f-152">Wytyczne dotyczące projektowania — projekt struktury</span><span class="sxs-lookup"><span data-stu-id="1ff7f-152">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="1ff7f-153">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="1ff7f-153">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)