---
description: modyfikator statyczny — odwołanie w C#
title: modyfikator statyczny — odwołanie w C#
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f42636d1bbdf4342297f46f50ec6dfc2a70eacad
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142066"
---
# <a name="static-c-reference"></a><span data-ttu-id="207c0-103">static (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="207c0-103">static (C# Reference)</span></span>

<span data-ttu-id="207c0-104">Na tej stronie omówiono `static` słowo kluczowe modyfikator.</span><span class="sxs-lookup"><span data-stu-id="207c0-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="207c0-105">`static`Słowo kluczowe jest również częścią [`using static`](using-static.md) dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="207c0-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="207c0-106">Użyj `static` modyfikatora, aby zadeklarować statyczną składową, która należy do samego typu, a nie do określonego obiektu.</span><span class="sxs-lookup"><span data-stu-id="207c0-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="207c0-107">`static`Modyfikator może służyć do deklarowania `static` klas.</span><span class="sxs-lookup"><span data-stu-id="207c0-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="207c0-108">W klasach, interfejsach i strukturach można dodać `static` modyfikator do pól, metod, właściwości, operatorów, zdarzeń i konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="207c0-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="207c0-109">`static`Modyfikator nie może być używany z indeksatorami lub finalizatorami.</span><span class="sxs-lookup"><span data-stu-id="207c0-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="207c0-110">Aby uzyskać więcej informacji, zobacz [klasy statyczne i statyczne elementy członkowskie klas](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="207c0-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="207c0-111">Przykład — Klasa statyczna</span><span class="sxs-lookup"><span data-stu-id="207c0-111">Example - static class</span></span>

<span data-ttu-id="207c0-112">Następująca Klasa jest zadeklarowana jako `static` i zawiera tylko `static` metody:</span><span class="sxs-lookup"><span data-stu-id="207c0-112">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="207c0-113">Deklaracja stałej lub typu jest niejawnie członkiem `static` .</span><span class="sxs-lookup"><span data-stu-id="207c0-113">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="207c0-114">`static`Nie można odwołać się do elementu członkowskiego za pomocą wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="207c0-114">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="207c0-115">Zamiast tego jest przywoływany przez nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="207c0-115">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="207c0-116">Rozważmy na przykład następujące klasy:</span><span class="sxs-lookup"><span data-stu-id="207c0-116">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="207c0-117">Aby odwołać się do `static` elementu członkowskiego `x` , należy użyć w pełni kwalifikowanej nazwy, `MyBaseC.MyStruct.x` chyba że element członkowski jest dostępny z tego samego zakresu:</span><span class="sxs-lookup"><span data-stu-id="207c0-117">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="207c0-118">Chociaż wystąpienie klasy zawiera oddzielną kopię wszystkich pól wystąpienia klasy, istnieje tylko jedna kopia każdego `static` pola.</span><span class="sxs-lookup"><span data-stu-id="207c0-118">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="207c0-119">Nie można użyć [`this`](this.md) w celu odwoływania się do `static` metod lub metody dostępu do właściwości.</span><span class="sxs-lookup"><span data-stu-id="207c0-119">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="207c0-120">Jeśli `static` słowo kluczowe jest stosowane do klasy, wszystkie elementy członkowskie klasy muszą mieć wartość `static` .</span><span class="sxs-lookup"><span data-stu-id="207c0-120">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="207c0-121">Klasy, interfejsy i `static` klasy mogą mieć `static` konstruktory.</span><span class="sxs-lookup"><span data-stu-id="207c0-121">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="207c0-122">`static`Konstruktor jest wywoływany w pewnym momencie od momentu uruchomienia programu i wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="207c0-122">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="207c0-123">`static`Słowo kluczowe ma bardziej ograniczone zastosowania niż w języku C++.</span><span class="sxs-lookup"><span data-stu-id="207c0-123">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="207c0-124">Aby porównać ze słowem kluczowym języka C++, zobacz [klasy magazynu (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="207c0-124">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="207c0-125">Aby przedstawić `static` członków, należy rozważyć klasę, która reprezentuje pracownika firmy.</span><span class="sxs-lookup"><span data-stu-id="207c0-125">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="207c0-126">Załóżmy, że Klasa zawiera metodę służącą do policzania pracowników i pola do przechowywania liczby pracowników.</span><span class="sxs-lookup"><span data-stu-id="207c0-126">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="207c0-127">Zarówno Metoda, jak i pole nie należy do żadnego wystąpienia jednego pracownika.</span><span class="sxs-lookup"><span data-stu-id="207c0-127">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="207c0-128">Zamiast tego należą do klasy pracowników jako całości.</span><span class="sxs-lookup"><span data-stu-id="207c0-128">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="207c0-129">Należy je zadeklarować jako `static` elementy członkowskie klasy.</span><span class="sxs-lookup"><span data-stu-id="207c0-129">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="207c0-130">Przykład — statyczne pole i Metoda</span><span class="sxs-lookup"><span data-stu-id="207c0-130">Example - static field and method</span></span>

<span data-ttu-id="207c0-131">Ten przykład odczytuje nazwę i identyfikator nowego pracownika, zwiększa licznik pracownika według jednego i wyświetla informacje dotyczące nowego pracownika oraz nową liczbę pracowników.</span><span class="sxs-lookup"><span data-stu-id="207c0-131">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="207c0-132">Ten program odczytuje bieżącą liczbę pracowników z klawiatury.</span><span class="sxs-lookup"><span data-stu-id="207c0-132">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="207c0-133">Przykład — Inicjalizacja statyczna</span><span class="sxs-lookup"><span data-stu-id="207c0-133">Example - static initialization</span></span>

<span data-ttu-id="207c0-134">Ten przykład pokazuje, że można zainicjować `static` pole przy użyciu innego `static` pola, które nie zostało jeszcze zadeklarowane.</span><span class="sxs-lookup"><span data-stu-id="207c0-134">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="207c0-135">Wyniki będą niezdefiniowane, dopóki nie zostanie jawnie przypisana wartość do `static` pola.</span><span class="sxs-lookup"><span data-stu-id="207c0-135">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="207c0-136">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="207c0-136">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="207c0-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="207c0-137">See also</span></span>

- [<span data-ttu-id="207c0-138">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="207c0-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="207c0-139">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="207c0-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="207c0-140">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="207c0-140">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="207c0-141">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="207c0-141">Modifiers</span></span>](index.md)
- [<span data-ttu-id="207c0-142">za pomocą dyrektywy static</span><span class="sxs-lookup"><span data-stu-id="207c0-142">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="207c0-143">Klasy statyczne i statyczni członkowie klas</span><span class="sxs-lookup"><span data-stu-id="207c0-143">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
