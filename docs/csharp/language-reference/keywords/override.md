---
description: override — modyfikator — odwołanie w C#
title: override — modyfikator — odwołanie w C#
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434876"
---
# <a name="override-c-reference"></a><span data-ttu-id="a6f28-103">override (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a6f28-103">override (C# reference)</span></span>

<span data-ttu-id="a6f28-104">`override`Modyfikator jest wymagany, aby zwiększyć lub zmodyfikować abstrakcyjną lub wirtualną implementację dziedziczonej metody, właściwości, indeksatora lub zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a6f28-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

<span data-ttu-id="a6f28-105">W poniższym przykładzie `Square` Klasa musi udostępniać zastąpioną implementację, `GetArea` ponieważ `GetArea` jest dziedziczona z klasy abstrakcyjnej `Shape` :</span><span class="sxs-lookup"><span data-stu-id="a6f28-105">In the following example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="a6f28-106">`override`Metoda zapewnia nową implementację metody dziedziczonej z klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="a6f28-106">An `override` method provides a new implementation of the method inherited from a base class.</span></span> <span data-ttu-id="a6f28-107">Metoda zastępowana przez `override` deklarację jest znana jako zastąpiona metoda podstawowa.</span><span class="sxs-lookup"><span data-stu-id="a6f28-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="a6f28-108">`override`Metoda musi mieć taką samą sygnaturę jak zastąpiona metoda podstawowa.</span><span class="sxs-lookup"><span data-stu-id="a6f28-108">An `override` method must have the same signature as the overridden base method.</span></span> <span data-ttu-id="a6f28-109">Począwszy od języka C# 9,0, `override` metody obsługują typy zwrotne typu współvariant.</span><span class="sxs-lookup"><span data-stu-id="a6f28-109">Beginning with C# 9.0, `override` methods support covariant return types.</span></span> <span data-ttu-id="a6f28-110">W szczególności zwracany typ `override` metody może pochodzić od typu zwracanego odpowiadającej metody podstawowej.</span><span class="sxs-lookup"><span data-stu-id="a6f28-110">In particular, the return type of an `override` method can derive from the return type of the corresponding base method.</span></span> <span data-ttu-id="a6f28-111">W języku C# 8,0 i starszych, zwracane typy `override` metody i zastąpiona metoda bazowa muszą być takie same.</span><span class="sxs-lookup"><span data-stu-id="a6f28-111">In C# 8.0 and earlier, the return types of an `override` method and the overridden base method must be the same.</span></span>

<span data-ttu-id="a6f28-112">Nie można zastąpić metody niewirtualnej lub statycznej.</span><span class="sxs-lookup"><span data-stu-id="a6f28-112">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="a6f28-113">Zastąpiona metoda bazowa musi mieć wartość `virtual` , `abstract` , lub `override` .</span><span class="sxs-lookup"><span data-stu-id="a6f28-113">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="a6f28-114">`override`Deklaracja nie może zmienić dostępności `virtual` metody.</span><span class="sxs-lookup"><span data-stu-id="a6f28-114">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="a6f28-115">Obie `override` metody i `virtual` metody muszą mieć ten sam [modyfikator poziomu dostępu](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a6f28-115">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="a6f28-116">Nie można użyć `new` `static` modyfikatora, lub, `virtual` Aby zmodyfikować `override` metodę.</span><span class="sxs-lookup"><span data-stu-id="a6f28-116">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="a6f28-117">Zastępowanie deklaracji właściwości musi określać dokładnie ten sam modyfikator dostępu, typ i nazwę, co Właściwość dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="a6f28-117">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property.</span></span> <span data-ttu-id="a6f28-118">Począwszy od języka C# 9,0, zastępowanie właściwości tylko do odczytu obsługuje typy zwrotne typu współvariant.</span><span class="sxs-lookup"><span data-stu-id="a6f28-118">Beginning with C# 9.0, read-only overriding properties support covariant return types.</span></span> <span data-ttu-id="a6f28-119">Zastąpiona właściwość musi mieć wartość `virtual` , `abstract` lub `override` .</span><span class="sxs-lookup"><span data-stu-id="a6f28-119">The overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="a6f28-120">Aby uzyskać więcej informacji na temat sposobu używania `override` słowa kluczowego, zobacz [przechowywanie wersji z przesłonięciami i nowymi słowami kluczowymi](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [wiedzą, kiedy używać przesłonięć i nowych słów kluczowych](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="a6f28-120">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span> <span data-ttu-id="a6f28-121">Aby uzyskać informacje na temat dziedziczenia, zobacz [dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="a6f28-121">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

## <a name="example"></a><span data-ttu-id="a6f28-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="a6f28-122">Example</span></span>

<span data-ttu-id="a6f28-123">W tym przykładzie zdefiniowano klasę bazową o nazwie `Employee` i klasę pochodną o nazwie `SalesEmployee` .</span><span class="sxs-lookup"><span data-stu-id="a6f28-123">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="a6f28-124">`SalesEmployee`Klasa zawiera dodatkowe pole, `salesbonus` i zastępuje metodę, `CalculatePay` Aby można było ją uwzględnić.</span><span class="sxs-lookup"><span data-stu-id="a6f28-124">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="a6f28-125">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a6f28-125">C# language specification</span></span>

<span data-ttu-id="a6f28-126">Aby uzyskać więcej informacji, zobacz sekcję [zastępowanie metod](~/_csharplang/spec/classes.md#override-methods) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a6f28-126">For more information, see the [Override methods](~/_csharplang/spec/classes.md#override-methods) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a6f28-127">Aby uzyskać więcej informacji na temat typów zwracanych z niezmiennymi, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span><span class="sxs-lookup"><span data-stu-id="a6f28-127">For more information about covariant return types, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f28-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a6f28-128">See also</span></span>

- [<span data-ttu-id="a6f28-129">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a6f28-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a6f28-130">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="a6f28-130">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="a6f28-131">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="a6f28-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a6f28-132">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="a6f28-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a6f28-133">streszczeń</span><span class="sxs-lookup"><span data-stu-id="a6f28-133">abstract</span></span>](abstract.md)
- [<span data-ttu-id="a6f28-134">virtual</span><span class="sxs-lookup"><span data-stu-id="a6f28-134">virtual</span></span>](virtual.md)
- [<span data-ttu-id="a6f28-135">New (modyfikator)</span><span class="sxs-lookup"><span data-stu-id="a6f28-135">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="a6f28-136">Polimorfizm</span><span class="sxs-lookup"><span data-stu-id="a6f28-136">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
