---
description: streszczenie — odwołanie w C#
title: streszczenie — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 276e3f6ab50a069e3852c529c13eaad3c64e42ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168884"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="099ec-103">abstract (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="099ec-103">abstract (C# Reference)</span></span>

<span data-ttu-id="099ec-104">`abstract`Modyfikator wskazuje, że modyfikowany element nie ma lub niekompletnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="099ec-104">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="099ec-105">Modyfikator abstrakcyjny może być używany z klasami, metodami, właściwościami, indeksatorami i zdarzeniami.</span><span class="sxs-lookup"><span data-stu-id="099ec-105">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="099ec-106">Użyj `abstract` modyfikatora w deklaracji klasy, aby wskazać, że Klasa jest przeznaczona tylko jako klasa bazowa innych klas, ale nie jest tworzona samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="099ec-106">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="099ec-107">Elementy członkowskie oznaczone jako abstrakcyjne muszą być zaimplementowane przez nieabstrakcyjne klasy, które pochodzą z klasy abstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="099ec-107">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="099ec-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="099ec-108">Example</span></span>  

 <span data-ttu-id="099ec-109">W tym przykładzie Klasa `Square` musi dostarczyć implementację, `GetArea` ponieważ pochodzi ona z `Shape` :</span><span class="sxs-lookup"><span data-stu-id="099ec-109">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="099ec-110">Klasy abstrakcyjne mają następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="099ec-110">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="099ec-111">Nie można utworzyć wystąpienia klasy abstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="099ec-111">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="099ec-112">Klasa abstrakcyjna może zawierać metody abstrakcyjne i metod dostępu.</span><span class="sxs-lookup"><span data-stu-id="099ec-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="099ec-113">Nie można zmodyfikować klasy abstrakcyjnej za pomocą modyfikatora [zapieczętowanego](./sealed.md) , ponieważ dwa Modyfikatory mają przeciwległe znaczenie.</span><span class="sxs-lookup"><span data-stu-id="099ec-113">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="099ec-114">`sealed`Modyfikator uniemożliwia dziedziczenie klasy, a `abstract` modyfikator wymaga klasy do dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="099ec-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="099ec-115">Klasa nieabstrakcyjna pochodna klasy abstrakcyjnej musi zawierać rzeczywiste implementacje wszystkich dziedziczonych metod abstrakcyjnych i metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="099ec-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="099ec-116">Użyj `abstract` modyfikatora w deklaracji metody lub właściwości, aby wskazać, że metoda lub właściwość nie zawiera implementacji.</span><span class="sxs-lookup"><span data-stu-id="099ec-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="099ec-117">Metody abstrakcyjne mają następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="099ec-117">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="099ec-118">Metoda abstrakcyjna jest niejawnie metodą wirtualną.</span><span class="sxs-lookup"><span data-stu-id="099ec-118">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="099ec-119">Deklaracje metody abstrakcyjnej są dozwolone tylko w klasach abstrakcyjnych.</span><span class="sxs-lookup"><span data-stu-id="099ec-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="099ec-120">Ponieważ Deklaracja metody abstrakcyjnej nie zapewnia rzeczywistej implementacji, nie istnieje treść metody; Deklaracja metody po prostu kończyć się średnikiem i nie ma nawiasów klamrowych ({}) po podpisie.</span><span class="sxs-lookup"><span data-stu-id="099ec-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="099ec-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="099ec-121">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="099ec-122">Implementacja jest dostarczana przez [przesłonięcie](./override.md)metody, która jest elementem członkowskim klasy nieabstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="099ec-122">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="099ec-123">Wystąpił błąd podczas używania modyfikatorów [static](./static.md) lub [Virtual](./virtual.md) w deklaracji metody abstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="099ec-123">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="099ec-124">Właściwości abstrakcyjne zachowują się jak metody abstrakcyjne, z wyjątkiem różnic w składni deklaracji i wywołania.</span><span class="sxs-lookup"><span data-stu-id="099ec-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="099ec-125">Wystąpił błąd podczas używania `abstract` modyfikatora dla właściwości statycznej.</span><span class="sxs-lookup"><span data-stu-id="099ec-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="099ec-126">Abstrakcyjna dziedziczona właściwość może zostać przesłonięta w klasie pochodnej przez dołączenie deklaracji właściwości, która używa modyfikatora [przesłaniania](./override.md) .</span><span class="sxs-lookup"><span data-stu-id="099ec-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="099ec-127">Aby uzyskać więcej informacji na temat klas abstrakcyjnych, zobacz [klasy abstrakcyjne i zapieczętowane oraz składowe klas](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="099ec-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="099ec-128">Klasa abstrakcyjna musi zapewniać implementację dla wszystkich elementów członkowskich interfejsu.</span><span class="sxs-lookup"><span data-stu-id="099ec-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="099ec-129">Klasa abstrakcyjna implementująca interfejs może mapować metody interfejsu na metody abstrakcyjne.</span><span class="sxs-lookup"><span data-stu-id="099ec-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="099ec-130">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="099ec-130">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="099ec-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="099ec-131">Example</span></span>  

 <span data-ttu-id="099ec-132">W tym przykładzie Klasa pochodzi `DerivedClass` od klasy abstrakcyjnej `BaseClass` .</span><span class="sxs-lookup"><span data-stu-id="099ec-132">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="099ec-133">Klasa abstrakcyjna zawiera metodę abstrakcyjną, `AbstractMethod` i dwie właściwości abstrakcyjne `X` oraz `Y` .</span><span class="sxs-lookup"><span data-stu-id="099ec-133">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="099ec-134">W poprzednim przykładzie, jeśli spróbujesz utworzyć wystąpienie klasy abstrakcyjnej przy użyciu instrukcji podobnej do:</span><span class="sxs-lookup"><span data-stu-id="099ec-134">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="099ec-135">Zostanie wyświetlony komunikat o błędzie informujący, że kompilator nie może utworzyć wystąpienia klasy abstrakcyjnej "BaseClass".</span><span class="sxs-lookup"><span data-stu-id="099ec-135">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="099ec-136">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="099ec-136">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="099ec-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="099ec-137">See also</span></span>

- [<span data-ttu-id="099ec-138">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="099ec-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="099ec-139">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="099ec-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="099ec-140">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="099ec-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="099ec-141">virtual</span><span class="sxs-lookup"><span data-stu-id="099ec-141">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="099ec-142">override</span><span class="sxs-lookup"><span data-stu-id="099ec-142">override</span></span>](./override.md)
- [<span data-ttu-id="099ec-143">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="099ec-143">C# Keywords</span></span>](./index.md)
