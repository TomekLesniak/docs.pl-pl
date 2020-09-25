---
title: Klasy abstrakcyjne i zapieczętowane oraz członkowie klas — Przewodnik programowania w języku C#
description: Abstrakcyjne słowo kluczowe w języku C# tworzy niekompletne klasy i składowe klas. Zapieczętowane słowo kluczowe uniemożliwia dziedziczenie wcześniej klas wirtualnych lub elementów członkowskich klas.
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: ccbc6734d4e9bafe059dd45bfdf82af7c84438a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204037"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="27803-104">Klasy abstrakcyjne i zapieczętowane oraz członkowie klas (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="27803-104">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>

<span data-ttu-id="27803-105">[Abstrakcyjne](../../language-reference/keywords/abstract.md) słowo kluczowe umożliwia tworzenie klas i składowych [klas](../../language-reference/keywords/class.md) , które są niekompletne i muszą być zaimplementowane w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="27803-105">The [abstract](../../language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="27803-106">[Zapieczętowane](../../language-reference/keywords/sealed.md) słowo kluczowe pozwala uniknąć dziedziczenia klasy lub niektórych elementów członkowskich klasy, które zostały wcześniej oznaczone jako [wirtualne](../../language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="27803-106">The [sealed](../../language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="27803-107">Klasy abstrakcyjne i składowe klas</span><span class="sxs-lookup"><span data-stu-id="27803-107">Abstract Classes and Class Members</span></span>  

 <span data-ttu-id="27803-108">Klasy mogą być deklarowane jako abstrakcyjne poprzez umieszczenie słowa kluczowego `abstract` przed definicją klasy.</span><span class="sxs-lookup"><span data-stu-id="27803-108">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="27803-109">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="27803-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 <span data-ttu-id="27803-110">Nie można utworzyć wystąpienia klasy abstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="27803-110">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="27803-111">Celem klasy abstrakcyjnej jest zapewnienie wspólnej definicji klasy bazowej, która może być współużytkowana przez wiele klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="27803-111">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="27803-112">Na przykład Biblioteka klas może definiować klasę abstrakcyjną, która jest używana jako parametr do wielu funkcji, i wymagać programiści używających tej biblioteki do zapewnienia własnej implementacji klasy przez utworzenie klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="27803-112">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="27803-113">Klasy abstrakcyjne mogą również definiować metody abstrakcyjne.</span><span class="sxs-lookup"><span data-stu-id="27803-113">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="27803-114">Jest to osiągane przez dodanie słowa kluczowego `abstract` przed typem zwracanym metody.</span><span class="sxs-lookup"><span data-stu-id="27803-114">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="27803-115">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="27803-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 <span data-ttu-id="27803-116">Metody abstrakcyjne nie mają implementacji, dlatego w definicji metody następuje średnik zamiast zwykłego bloku metody.</span><span class="sxs-lookup"><span data-stu-id="27803-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="27803-117">Klasy pochodne klasy abstrakcyjnej muszą implementować wszystkie metody abstrakcyjne.</span><span class="sxs-lookup"><span data-stu-id="27803-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="27803-118">Gdy Klasa abstrakcyjna dziedziczy metodę wirtualną z klasy bazowej, Klasa abstrakcyjna może zastąpić metodę wirtualną metodą abstrakcyjną.</span><span class="sxs-lookup"><span data-stu-id="27803-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="27803-119">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="27803-119">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 <span data-ttu-id="27803-120">Jeśli `virtual` Metoda jest zadeklarowana `abstract` , jest nadal wirtualna dla każdej klasy dziedziczące z klasy abstrakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="27803-120">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="27803-121">Klasa dziedziczące metodę abstrakcyjną nie może uzyskać dostępu do oryginalnej implementacji metody — w poprzednim przykładzie w `DoWork` klasie F nie można wywołać `DoWork` klasy D. W ten sposób Klasa abstrakcyjna może wymusić, aby klasy pochodne zapewniały nowe implementacje metod wirtualnych.</span><span class="sxs-lookup"><span data-stu-id="27803-121">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="27803-122">Klasy zapieczętowane i składowe klas</span><span class="sxs-lookup"><span data-stu-id="27803-122">Sealed Classes and Class Members</span></span>  

 <span data-ttu-id="27803-123">Klasy mogą być deklarowane jako [zapieczętowane](../../language-reference/keywords/sealed.md) poprzez umieszczenie słowa kluczowego `sealed` przed definicją klasy.</span><span class="sxs-lookup"><span data-stu-id="27803-123">Classes can be declared as [sealed](../../language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="27803-124">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="27803-124">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 <span data-ttu-id="27803-125">Klasa zapieczętowana nie może być używana jako klasa bazowa.</span><span class="sxs-lookup"><span data-stu-id="27803-125">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="27803-126">Z tego powodu nie może być również klasą abstrakcyjną.</span><span class="sxs-lookup"><span data-stu-id="27803-126">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="27803-127">Zapieczętowane klasy uniemożliwiają wyprowadzanie.</span><span class="sxs-lookup"><span data-stu-id="27803-127">Sealed classes prevent derivation.</span></span> <span data-ttu-id="27803-128">Ponieważ nigdy nie mogą być używane jako klasa bazowa, niektóre optymalizacje w czasie wykonywania mogą znacznie przyspieszyć wywoływanie zapieczętowanych elementów członkowskich klas.</span><span class="sxs-lookup"><span data-stu-id="27803-128">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="27803-129">Metoda, indeksator, właściwość lub zdarzenie w klasie pochodnej, która zastępuje wirtualną składową klasy bazowej, może zadeklarować ten element jako zapieczętowany.</span><span class="sxs-lookup"><span data-stu-id="27803-129">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="27803-130">Spowoduje to negację wirtualnego aspektu elementu członkowskiego dla żadnej dalszej klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="27803-130">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="27803-131">Jest to realizowane przez umieszczenie `sealed` słowa kluczowego przed słowem kluczowym [override](../../language-reference/keywords/override.md) w deklaracji składowej klasy.</span><span class="sxs-lookup"><span data-stu-id="27803-131">This is accomplished by putting the `sealed` keyword before the [override](../../language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="27803-132">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="27803-132">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="27803-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27803-133">See also</span></span>

- [<span data-ttu-id="27803-134">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="27803-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27803-135">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="27803-135">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="27803-136">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="27803-136">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="27803-137">Metody</span><span class="sxs-lookup"><span data-stu-id="27803-137">Methods</span></span>](./methods.md)
- [<span data-ttu-id="27803-138">Pola</span><span class="sxs-lookup"><span data-stu-id="27803-138">Fields</span></span>](./fields.md)
- [<span data-ttu-id="27803-139">Porada: definiowanie właściwości abstrakcyjnych</span><span class="sxs-lookup"><span data-stu-id="27803-139">How to define abstract properties</span></span>](./how-to-define-abstract-properties.md)
