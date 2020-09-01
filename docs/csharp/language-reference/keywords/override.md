---
description: override — modyfikator — odwołanie w C#
title: override — modyfikator — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 51ca806310214981b7ff24a796fe078d902dca4d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134462"
---
# <a name="override-c-reference"></a><span data-ttu-id="089c9-103">override (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="089c9-103">override (C# Reference)</span></span>

<span data-ttu-id="089c9-104">`override`Modyfikator jest wymagany, aby zwiększyć lub zmodyfikować abstrakcyjną lub wirtualną implementację dziedziczonej metody, właściwości, indeksatora lub zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="089c9-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="089c9-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="089c9-105">Example</span></span>

<span data-ttu-id="089c9-106">W tym przykładzie `Square` Klasa musi udostępniać zastąpioną implementację, `GetArea` ponieważ `GetArea` jest dziedziczona z klasy abstrakcyjnej `Shape` :</span><span class="sxs-lookup"><span data-stu-id="089c9-106">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="089c9-107">`override`Metoda zapewnia nową implementację elementu członkowskiego, który jest Dziedziczony z klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="089c9-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="089c9-108">Metoda zastępowana przez `override` deklarację jest znana jako zastąpiona metoda podstawowa.</span><span class="sxs-lookup"><span data-stu-id="089c9-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="089c9-109">Zastąpiona metoda bazowa musi mieć taką samą sygnaturę jak `override` Metoda.</span><span class="sxs-lookup"><span data-stu-id="089c9-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="089c9-110">Aby uzyskać informacje na temat dziedziczenia, zobacz [dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="089c9-110">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="089c9-111">Nie można zastąpić metody niewirtualnej lub statycznej.</span><span class="sxs-lookup"><span data-stu-id="089c9-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="089c9-112">Zastąpiona metoda bazowa musi mieć wartość `virtual` , `abstract` , lub `override` .</span><span class="sxs-lookup"><span data-stu-id="089c9-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="089c9-113">`override`Deklaracja nie może zmienić dostępności `virtual` metody.</span><span class="sxs-lookup"><span data-stu-id="089c9-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="089c9-114">Obie `override` metody i `virtual` metody muszą mieć ten sam [modyfikator poziomu dostępu](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="089c9-114">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="089c9-115">Nie można użyć `new` `static` modyfikatora, lub, `virtual` Aby zmodyfikować `override` metodę.</span><span class="sxs-lookup"><span data-stu-id="089c9-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="089c9-116">Zastępowanie deklaracji właściwości musi określać dokładnie ten sam modyfikator dostępu, typ i nazwę, co Właściwość dziedziczona, a zastąpiona właściwość musi mieć wartość `virtual` , `abstract` lub `override` .</span><span class="sxs-lookup"><span data-stu-id="089c9-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="089c9-117">Aby uzyskać więcej informacji na temat sposobu używania `override` słowa kluczowego, zobacz [przechowywanie wersji z przesłonięciami i nowymi słowami kluczowymi](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [wiedzą, kiedy używać przesłonięć i nowych słów kluczowych](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="089c9-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="089c9-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="089c9-118">Example</span></span>

<span data-ttu-id="089c9-119">W tym przykładzie zdefiniowano klasę bazową o nazwie `Employee` i klasę pochodną o nazwie `SalesEmployee` .</span><span class="sxs-lookup"><span data-stu-id="089c9-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="089c9-120">`SalesEmployee`Klasa zawiera dodatkowe pole, `salesbonus` i zastępuje metodę, `CalculatePay` Aby można było ją uwzględnić.</span><span class="sxs-lookup"><span data-stu-id="089c9-120">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="089c9-121">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="089c9-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="089c9-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="089c9-122">See also</span></span>

- [<span data-ttu-id="089c9-123">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="089c9-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="089c9-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="089c9-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="089c9-125">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="089c9-125">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="089c9-126">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="089c9-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="089c9-127">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="089c9-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="089c9-128">streszczeń</span><span class="sxs-lookup"><span data-stu-id="089c9-128">abstract</span></span>](abstract.md)
- [<span data-ttu-id="089c9-129">virtual</span><span class="sxs-lookup"><span data-stu-id="089c9-129">virtual</span></span>](virtual.md)
- [<span data-ttu-id="089c9-130">New (modyfikator)</span><span class="sxs-lookup"><span data-stu-id="089c9-130">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="089c9-131">Polimorfizm</span><span class="sxs-lookup"><span data-stu-id="089c9-131">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
