---
title: Jak dodać metody niestandardowe dla zapytań LINQ (C#)
description: Dowiedz się, jak przedłużyć składnię zapytań LINQ, dodając metody rozszerzające do <T> interfejsu IEnumerable w języku C#.
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122429"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="04d64-103">Jak dodać metody niestandardowe dla zapytań LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="04d64-103">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="04d64-104">Rozszerzasz zestaw metod używanych przez zapytania LINQ przez dodawanie metod rozszerzających do <xref:System.Collections.Generic.IEnumerable%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="04d64-104">You extend the set of methods that you use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="04d64-105">Na przykład oprócz standardowej średniej lub maksymalnej operacji można utworzyć niestandardową metodę agregującą w celu obliczenia pojedynczej wartości z sekwencji wartości.</span><span class="sxs-lookup"><span data-stu-id="04d64-105">For example, in addition to the standard average or maximum operations, you create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="04d64-106">Należy również utworzyć metodę, która działa jako filtr niestandardowy lub określona transformacja danych dla sekwencji wartości i zwraca nową sekwencję.</span><span class="sxs-lookup"><span data-stu-id="04d64-106">You also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="04d64-107">Przykładami takich metod są <xref:System.Linq.Enumerable.Distinct%2A> , <xref:System.Linq.Enumerable.Skip%2A> , i <xref:System.Linq.Enumerable.Reverse%2A> .</span><span class="sxs-lookup"><span data-stu-id="04d64-107">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="04d64-108">Rozszerzając <xref:System.Collections.Generic.IEnumerable%601> interfejs, można zastosować niestandardowe metody do dowolnej wyliczalnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="04d64-108">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="04d64-109">Aby uzyskać więcej informacji, zobacz [metody rozszerzenia](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="04d64-109">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="04d64-110">Dodawanie metody agregującej</span><span class="sxs-lookup"><span data-stu-id="04d64-110">Adding an aggregate method</span></span>

<span data-ttu-id="04d64-111">Metoda agregująca oblicza pojedynczą wartość z zestawu wartości.</span><span class="sxs-lookup"><span data-stu-id="04d64-111">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="04d64-112">LINQ zawiera kilka metod agregujących, w tym <xref:System.Linq.Enumerable.Average%2A> , <xref:System.Linq.Enumerable.Min%2A> i <xref:System.Linq.Enumerable.Max%2A> .</span><span class="sxs-lookup"><span data-stu-id="04d64-112">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="04d64-113">Można utworzyć własną metodę agregującą, dodając metodę rozszerzenia do <xref:System.Collections.Generic.IEnumerable%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="04d64-113">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="04d64-114">Poniższy przykład kodu pokazuje, jak utworzyć metodę rozszerzenia wywołana, `Median` Aby obliczyć medianę dla sekwencji liczb typu `double` .</span><span class="sxs-lookup"><span data-stu-id="04d64-114">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

<span data-ttu-id="04d64-115">Ta metoda rozszerzenia jest wywoływana dla każdej wyliczalnej kolekcji w taki sam sposób, w jaki wywołujemy inne metody agregacji z <xref:System.Collections.Generic.IEnumerable%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="04d64-115">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="04d64-116">Poniższy przykład kodu pokazuje, jak używać `Median` metody dla tablicy typu `double` .</span><span class="sxs-lookup"><span data-stu-id="04d64-116">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="04d64-117">Przeciążanie metody agregującej w celu zaakceptowania różnych typów</span><span class="sxs-lookup"><span data-stu-id="04d64-117">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="04d64-118">Można przeciążyć metodę agregacji, aby akceptować sekwencje różnych typów.</span><span class="sxs-lookup"><span data-stu-id="04d64-118">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="04d64-119">Standardowe podejście polega na utworzeniu przeciążenia dla każdego typu.</span><span class="sxs-lookup"><span data-stu-id="04d64-119">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="04d64-120">Innym rozwiązaniem jest utworzenie przeciążenia, które będzie miało typ ogólny i przekonwertować go na określony typ za pomocą delegata.</span><span class="sxs-lookup"><span data-stu-id="04d64-120">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="04d64-121">Można również połączyć oba podejścia.</span><span class="sxs-lookup"><span data-stu-id="04d64-121">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="04d64-122">Aby utworzyć Przeciążenie dla każdego typu</span><span class="sxs-lookup"><span data-stu-id="04d64-122">To create an overload for each type</span></span>

<span data-ttu-id="04d64-123">Można utworzyć określone Przeciążenie dla każdego typu, który ma być obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="04d64-123">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="04d64-124">Poniższy przykład kodu przedstawia Przeciążenie `Median` metody dla `int` typu.</span><span class="sxs-lookup"><span data-stu-id="04d64-124">The following code example shows an overload of the `Median` method for the `int` type.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

<span data-ttu-id="04d64-125">Teraz można wywoływać `Median` przeciążenia dla obu `integer` typów i `double` typy, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="04d64-125">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="04d64-126">Aby utworzyć Przeciążenie ogólne</span><span class="sxs-lookup"><span data-stu-id="04d64-126">To create a generic overload</span></span>

<span data-ttu-id="04d64-127">Można również utworzyć Przeciążenie, które akceptuje sekwencję obiektów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="04d64-127">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="04d64-128">To przeciążenie przyjmuje delegat jako parametr i używa go do konwersji sekwencji obiektów typu ogólnego do określonego typu.</span><span class="sxs-lookup"><span data-stu-id="04d64-128">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="04d64-129">Poniższy kod przedstawia Przeciążenie `Median` metody, która przyjmuje <xref:System.Func%602> Delegat jako parametr.</span><span class="sxs-lookup"><span data-stu-id="04d64-129">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="04d64-130">Ten delegat pobiera obiekt typu ogólnego T i zwraca obiekt typu `double` .</span><span class="sxs-lookup"><span data-stu-id="04d64-130">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

<span data-ttu-id="04d64-131">Teraz można wywołać `Median` metodę dla sekwencji obiektów dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="04d64-131">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="04d64-132">Jeśli typ nie ma własnego przeciążenia metody, należy przekazać parametr delegata.</span><span class="sxs-lookup"><span data-stu-id="04d64-132">If the type doesn't have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="04d64-133">W języku C# można użyć wyrażenia lambda do tego celu.</span><span class="sxs-lookup"><span data-stu-id="04d64-133">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="04d64-134">Ponadto, tylko w Visual Basic, jeśli używasz `Aggregate` `Group By` klauzuli or zamiast wywołania metody, można przekazać dowolną wartość lub wyrażenie, które znajduje się w zakresie tej klauzuli.</span><span class="sxs-lookup"><span data-stu-id="04d64-134">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="04d64-135">Poniższy przykładowy kod pokazuje, jak wywołać `Median` metodę dla tablicy liczb całkowitych i tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="04d64-135">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="04d64-136">Dla ciągów, mediany dla długości ciągów w tablicy jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="04d64-136">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="04d64-137">W przykładzie pokazano, jak przekazać <xref:System.Func%602> parametr delegata do `Median` metody dla każdego przypadku.</span><span class="sxs-lookup"><span data-stu-id="04d64-137">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a><span data-ttu-id="04d64-138">Dodawanie metody zwracającej sekwencję</span><span class="sxs-lookup"><span data-stu-id="04d64-138">Adding a method that returns a sequence</span></span>

<span data-ttu-id="04d64-139">Interfejs można rozszerzyć <xref:System.Collections.Generic.IEnumerable%601> za pomocą niestandardowej metody zapytania, która zwraca sekwencję wartości.</span><span class="sxs-lookup"><span data-stu-id="04d64-139">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="04d64-140">W tym przypadku metoda musi zwracać kolekcję typu <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="04d64-140">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="04d64-141">Takie metody mogą służyć do zastosowania filtrów lub transformacji danych do sekwencji wartości.</span><span class="sxs-lookup"><span data-stu-id="04d64-141">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="04d64-142">Poniższy przykład pokazuje, jak utworzyć metodę rozszerzenia o nazwie `AlternateElements` , która zwraca każdy inny element w kolekcji, rozpoczynając od pierwszego elementu.</span><span class="sxs-lookup"><span data-stu-id="04d64-142">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

<span data-ttu-id="04d64-143">Można wywołać tę metodę rozszerzenia dla każdej wyliczalnej kolekcji tak samo jak w przypadku wywołania innych metod z <xref:System.Collections.Generic.IEnumerable%601> interfejsu, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="04d64-143">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a><span data-ttu-id="04d64-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04d64-144">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="04d64-145">Metody rozszerzania</span><span class="sxs-lookup"><span data-stu-id="04d64-145">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
