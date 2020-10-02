---
description: modyfikator statyczny — odwołanie w C#
title: modyfikator statyczny — odwołanie w C#
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 239163fc2f91ccbfe8b1c111a358db87d36a8308
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654642"
---
# <a name="static-c-reference"></a><span data-ttu-id="143ff-103">static (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="143ff-103">static (C# Reference)</span></span>

<span data-ttu-id="143ff-104">Na tej stronie omówiono `static` słowo kluczowe modyfikator.</span><span class="sxs-lookup"><span data-stu-id="143ff-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="143ff-105">`static`Słowo kluczowe jest również częścią [`using static`](using-static.md) dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="143ff-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="143ff-106">Użyj `static` modyfikatora, aby zadeklarować statyczną składową, która należy do samego typu, a nie do określonego obiektu.</span><span class="sxs-lookup"><span data-stu-id="143ff-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="143ff-107">`static`Modyfikator może służyć do deklarowania `static` klas.</span><span class="sxs-lookup"><span data-stu-id="143ff-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="143ff-108">W klasach, interfejsach i strukturach można dodać `static` modyfikator do pól, metod, właściwości, operatorów, zdarzeń i konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="143ff-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="143ff-109">`static`Modyfikator nie może być używany z indeksatorami lub finalizatorami.</span><span class="sxs-lookup"><span data-stu-id="143ff-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="143ff-110">Aby uzyskać więcej informacji, zobacz [klasy statyczne i statyczne elementy członkowskie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="143ff-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="143ff-111">Począwszy od języka C# 8,0, można dodać `static` modyfikator do [funkcji lokalnej](../../programming-guide/classes-and-structs/local-functions.md).</span><span class="sxs-lookup"><span data-stu-id="143ff-111">Beginning with C# 8.0, you can add the `static` modifier to a [local function](../../programming-guide/classes-and-structs/local-functions.md).</span></span> <span data-ttu-id="143ff-112">Statyczna funkcja lokalna nie może przechwycić lokalnych zmiennych lub stanu wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="143ff-112">A static local function can't capture local variables or instance state.</span></span>

<span data-ttu-id="143ff-113">Począwszy od języka C# 9,0, można dodać `static` modyfikator do [wyrażenia lambda](../operators/lambda-expressions.md) lub [metody anonimowej](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="143ff-113">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="143ff-114">Statyczna metoda lambda lub anonimowa nie może przechwycić lokalnych zmiennych lub stanu wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="143ff-114">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="143ff-115">Przykład — Klasa statyczna</span><span class="sxs-lookup"><span data-stu-id="143ff-115">Example - static class</span></span>

<span data-ttu-id="143ff-116">Następująca Klasa jest zadeklarowana jako `static` i zawiera tylko `static` metody:</span><span class="sxs-lookup"><span data-stu-id="143ff-116">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="143ff-117">Deklaracja stałej lub typu jest niejawnie członkiem `static` .</span><span class="sxs-lookup"><span data-stu-id="143ff-117">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="143ff-118">`static`Nie można odwołać się do elementu członkowskiego za pomocą wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="143ff-118">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="143ff-119">Zamiast tego jest przywoływany przez nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="143ff-119">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="143ff-120">Rozważmy na przykład następujące klasy:</span><span class="sxs-lookup"><span data-stu-id="143ff-120">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="143ff-121">Aby odwołać się do `static` elementu członkowskiego `x` , należy użyć w pełni kwalifikowanej nazwy, `MyBaseC.MyStruct.x` chyba że element członkowski jest dostępny z tego samego zakresu:</span><span class="sxs-lookup"><span data-stu-id="143ff-121">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="143ff-122">Chociaż wystąpienie klasy zawiera oddzielną kopię wszystkich pól wystąpienia klasy, istnieje tylko jedna kopia każdego `static` pola.</span><span class="sxs-lookup"><span data-stu-id="143ff-122">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="143ff-123">Nie można użyć [`this`](this.md) w celu odwoływania się do `static` metod lub metody dostępu do właściwości.</span><span class="sxs-lookup"><span data-stu-id="143ff-123">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="143ff-124">Jeśli `static` słowo kluczowe jest stosowane do klasy, wszystkie elementy członkowskie klasy muszą mieć wartość `static` .</span><span class="sxs-lookup"><span data-stu-id="143ff-124">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="143ff-125">Klasy, interfejsy i `static` klasy mogą mieć `static` konstruktory.</span><span class="sxs-lookup"><span data-stu-id="143ff-125">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="143ff-126">`static`Konstruktor jest wywoływany w pewnym momencie od momentu uruchomienia programu i wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="143ff-126">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="143ff-127">`static`Słowo kluczowe ma bardziej ograniczone zastosowania niż w języku C++.</span><span class="sxs-lookup"><span data-stu-id="143ff-127">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="143ff-128">Aby porównać ze słowem kluczowym języka C++, zobacz [klasy magazynu (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="143ff-128">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="143ff-129">Aby przedstawić `static` członków, należy rozważyć klasę, która reprezentuje pracownika firmy.</span><span class="sxs-lookup"><span data-stu-id="143ff-129">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="143ff-130">Załóżmy, że Klasa zawiera metodę służącą do policzania pracowników i pola do przechowywania liczby pracowników.</span><span class="sxs-lookup"><span data-stu-id="143ff-130">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="143ff-131">Zarówno Metoda, jak i pole nie należy do żadnego wystąpienia jednego pracownika.</span><span class="sxs-lookup"><span data-stu-id="143ff-131">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="143ff-132">Zamiast tego należą do klasy pracowników jako całości.</span><span class="sxs-lookup"><span data-stu-id="143ff-132">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="143ff-133">Należy je zadeklarować jako `static` elementy członkowskie klasy.</span><span class="sxs-lookup"><span data-stu-id="143ff-133">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="143ff-134">Przykład — statyczne pole i Metoda</span><span class="sxs-lookup"><span data-stu-id="143ff-134">Example - static field and method</span></span>

<span data-ttu-id="143ff-135">Ten przykład odczytuje nazwę i identyfikator nowego pracownika, zwiększa licznik pracownika według jednego i wyświetla informacje dotyczące nowego pracownika oraz nową liczbę pracowników.</span><span class="sxs-lookup"><span data-stu-id="143ff-135">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="143ff-136">Ten program odczytuje bieżącą liczbę pracowników z klawiatury.</span><span class="sxs-lookup"><span data-stu-id="143ff-136">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="143ff-137">Przykład — Inicjalizacja statyczna</span><span class="sxs-lookup"><span data-stu-id="143ff-137">Example - static initialization</span></span>

<span data-ttu-id="143ff-138">Ten przykład pokazuje, że można zainicjować `static` pole przy użyciu innego `static` pola, które nie zostało jeszcze zadeklarowane.</span><span class="sxs-lookup"><span data-stu-id="143ff-138">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="143ff-139">Wyniki będą niezdefiniowane, dopóki nie zostanie jawnie przypisana wartość do `static` pola.</span><span class="sxs-lookup"><span data-stu-id="143ff-139">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="143ff-140">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="143ff-140">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="143ff-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="143ff-141">See also</span></span>

- [<span data-ttu-id="143ff-142">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="143ff-142">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="143ff-143">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="143ff-143">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="143ff-144">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="143ff-144">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="143ff-145">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="143ff-145">Modifiers</span></span>](index.md)
- [<span data-ttu-id="143ff-146">za pomocą dyrektywy static</span><span class="sxs-lookup"><span data-stu-id="143ff-146">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="143ff-147">Klasy statyczne i statyczni członkowie klas</span><span class="sxs-lookup"><span data-stu-id="143ff-147">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
