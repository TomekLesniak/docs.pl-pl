---
title: Współpraca z kolekcjami — wprowadzenie do samouczka języka C#
description: Poznaj język C#, eksplorując kolekcję list w tym samouczku.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: e2282df21420630634911e07f4fb3b94f34a792b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414686"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="19468-103">Dowiedz się, jak zarządzać kolekcjami danych przy użyciu typu listy ogólnej</span><span class="sxs-lookup"><span data-stu-id="19468-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="19468-104">Ten samouczek wprowadzający zawiera wprowadzenie do języka C# i podstawowe informacje o <xref:System.Collections.Generic.List%601> klasie.</span><span class="sxs-lookup"><span data-stu-id="19468-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="19468-105">Ten samouczek oczekuje, że masz maszynę, której możesz użyć do programowania.</span><span class="sxs-lookup"><span data-stu-id="19468-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="19468-106">Samouczek platformy .NET [Hello World w ciągu 10 minut](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) zawiera instrukcje dotyczące konfigurowania lokalnego środowiska deweloperskiego w systemie Windows, Linux lub macOS.</span><span class="sxs-lookup"><span data-stu-id="19468-106">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="19468-107">Szybki przegląd poleceń, które będą używane, jest [znany z narzędziami programistycznymi](local-environment.md)z linkami do dodatkowych informacji.</span><span class="sxs-lookup"><span data-stu-id="19468-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="19468-108">Przykład listy podstawowej</span><span class="sxs-lookup"><span data-stu-id="19468-108">A basic list example</span></span>

<span data-ttu-id="19468-109">Utwórz katalog o nazwie *list-samouczek*.</span><span class="sxs-lookup"><span data-stu-id="19468-109">Create a directory named *list-tutorial*.</span></span> <span data-ttu-id="19468-110">Upewnij się, że bieżący katalog jest uruchomiony `dotnet new console` .</span><span class="sxs-lookup"><span data-stu-id="19468-110">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="19468-111">Otwórz *program.cs* w ulubionym edytorze i Zastąp istniejący kod następującym:</span><span class="sxs-lookup"><span data-stu-id="19468-111">Open *Program.cs* in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="19468-112">Zamień `<name>` na nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="19468-112">Replace `<name>` with your name.</span></span> <span data-ttu-id="19468-113">Zapisz plik *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="19468-113">Save *Program.cs*.</span></span> <span data-ttu-id="19468-114">Wpisz `dotnet run` w oknie konsoli, aby ją wypróbować.</span><span class="sxs-lookup"><span data-stu-id="19468-114">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="19468-115">Utworzono listę ciągów, dodano trzy nazwy do tej listy i wydrukowanych nazw we wszystkich WERSALIKach.</span><span class="sxs-lookup"><span data-stu-id="19468-115">You've created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="19468-116">Są używane koncepcje, które zostały uzyskane we wcześniejszych samouczkach, aby przepętlać listę.</span><span class="sxs-lookup"><span data-stu-id="19468-116">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="19468-117">Kod do wyświetlania nazw korzysta z funkcji [interpolacji ciągów](../../language-reference/tokens/interpolated.md) .</span><span class="sxs-lookup"><span data-stu-id="19468-117">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="19468-118">Gdy poprzedzasz `string` `$` znak, możesz osadzić kod w języku C# w deklaracji ciągu.</span><span class="sxs-lookup"><span data-stu-id="19468-118">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="19468-119">Rzeczywisty ciąg zastępuje ten kod C# wartością, którą generuje.</span><span class="sxs-lookup"><span data-stu-id="19468-119">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="19468-120">W tym przykładzie zastępuje on `{name.ToUpper()}` każdą nazwę, przekonwertowane na wielkie litery, ponieważ wywołano <xref:System.String.ToUpper%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="19468-120">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="19468-121">Kontynuujmy Eksplorowanie.</span><span class="sxs-lookup"><span data-stu-id="19468-121">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="19468-122">Modyfikuj zawartość listy</span><span class="sxs-lookup"><span data-stu-id="19468-122">Modify list contents</span></span>

<span data-ttu-id="19468-123">Utworzona kolekcja używa <xref:System.Collections.Generic.List%601> typu.</span><span class="sxs-lookup"><span data-stu-id="19468-123">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="19468-124">Ten typ przechowuje sekwencje elementów.</span><span class="sxs-lookup"><span data-stu-id="19468-124">This type stores sequences of elements.</span></span> <span data-ttu-id="19468-125">Należy określić typ elementów między nawiasami kątowymi.</span><span class="sxs-lookup"><span data-stu-id="19468-125">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="19468-126">Jednym z ważnych aspektów tego <xref:System.Collections.Generic.List%601> typu jest to, że można go zwiększyć lub zmniejszyć, umożliwiając dodawanie lub usuwanie elementów.</span><span class="sxs-lookup"><span data-stu-id="19468-126">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="19468-127">Dodaj ten kod przed zamknięciem `}` `Main` metody:</span><span class="sxs-lookup"><span data-stu-id="19468-127">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="19468-128">Dodano dwie więcej nazw na końcu listy.</span><span class="sxs-lookup"><span data-stu-id="19468-128">You've added two more names to the end of the list.</span></span> <span data-ttu-id="19468-129">Również został także usunięty.</span><span class="sxs-lookup"><span data-stu-id="19468-129">You've also removed one as well.</span></span> <span data-ttu-id="19468-130">Zapisz plik i wpisz, `dotnet run` Aby go wypróbować.</span><span class="sxs-lookup"><span data-stu-id="19468-130">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="19468-131"><xref:System.Collections.Generic.List%601>Umożliwia także odwoływanie się do poszczególnych elementów według **indeksu** .</span><span class="sxs-lookup"><span data-stu-id="19468-131">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="19468-132">Indeks między `[` i `]` tokenami należy umieścić po nazwie listy.</span><span class="sxs-lookup"><span data-stu-id="19468-132">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="19468-133">Język C# używa wartości 0 jako pierwszego indeksu.</span><span class="sxs-lookup"><span data-stu-id="19468-133">C# uses 0 for the first index.</span></span> <span data-ttu-id="19468-134">Dodaj ten kod bezpośrednio poniżej kodu, który właśnie został dodany, i wypróbuj go:</span><span class="sxs-lookup"><span data-stu-id="19468-134">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="19468-135">Nie można uzyskać dostępu do indeksu poza końcem listy.</span><span class="sxs-lookup"><span data-stu-id="19468-135">You can't access an index beyond the end of the list.</span></span> <span data-ttu-id="19468-136">Pamiętaj, że indeksy zaczynają się od 0, więc największy prawidłowy indeks jest mniejszy od liczby elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="19468-136">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="19468-137">Możesz sprawdzić, jak długo lista używa <xref:System.Collections.Generic.List%601.Count%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="19468-137">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="19468-138">Dodaj następujący kod na końcu metody Main:</span><span class="sxs-lookup"><span data-stu-id="19468-138">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="19468-139">Zapisz plik i wpisz ponownie, `dotnet run` Aby zobaczyć wyniki.</span><span class="sxs-lookup"><span data-stu-id="19468-139">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="19468-140">Wyszukiwanie i sortowanie list</span><span class="sxs-lookup"><span data-stu-id="19468-140">Search and sort lists</span></span>

<span data-ttu-id="19468-141">Nasze przykłady używają stosunkowo małych list, ale aplikacje mogą często tworzyć listy z wieloma elementami, czasami numerowania w tysiącach.</span><span class="sxs-lookup"><span data-stu-id="19468-141">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="19468-142">Aby znaleźć elementy w tych większych kolekcjach, należy przeszukać listę pod kątem różnych elementów.</span><span class="sxs-lookup"><span data-stu-id="19468-142">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="19468-143"><xref:System.Collections.Generic.List%601.IndexOf%2A>Metoda wyszukuje element i zwraca indeks elementu.</span><span class="sxs-lookup"><span data-stu-id="19468-143">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="19468-144">Jeśli element nie znajduje się na liście, `IndexOf` zwraca `-1` .</span><span class="sxs-lookup"><span data-stu-id="19468-144">If the item isn't in the list, `IndexOf` returns `-1`.</span></span> <span data-ttu-id="19468-145">Dodaj ten kod na końcu `Main` metody:</span><span class="sxs-lookup"><span data-stu-id="19468-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="19468-146">Elementy na liście można także sortować.</span><span class="sxs-lookup"><span data-stu-id="19468-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="19468-147"><xref:System.Collections.Generic.List%601.Sort%2A>Metoda sortuje wszystkie elementy na liście w ich normalnej kolejności (alfabetycznie w przypadku ciągów).</span><span class="sxs-lookup"><span data-stu-id="19468-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically for strings).</span></span> <span data-ttu-id="19468-148">Dodaj ten kod na końcu naszej `Main` metody:</span><span class="sxs-lookup"><span data-stu-id="19468-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="19468-149">Zapisz plik i wpisz, `dotnet run` Aby wypróbować tę najnowszą wersję.</span><span class="sxs-lookup"><span data-stu-id="19468-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="19468-150">Przed rozpoczęciem następnej sekcji przechodźmy bieżący kod w oddzielną metodę.</span><span class="sxs-lookup"><span data-stu-id="19468-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="19468-151">Ułatwia to rozpoczęcie pracy z nowym przykładem.</span><span class="sxs-lookup"><span data-stu-id="19468-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="19468-152">Zmień nazwę `Main` metody na `WorkingWithStrings` i Napisz nową `Main` metodę, która wywołuje `WorkingWithStrings` .</span><span class="sxs-lookup"><span data-stu-id="19468-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="19468-153">Po zakończeniu kod powinien wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="19468-153">When you've finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="19468-154">Listy innych typów</span><span class="sxs-lookup"><span data-stu-id="19468-154">Lists of other types</span></span>

<span data-ttu-id="19468-155">Używasz `string` typu na listach do tej pory.</span><span class="sxs-lookup"><span data-stu-id="19468-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="19468-156">Użyjmy <xref:System.Collections.Generic.List%601> innego typu.</span><span class="sxs-lookup"><span data-stu-id="19468-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="19468-157">Utwórzmy zestaw numerów.</span><span class="sxs-lookup"><span data-stu-id="19468-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="19468-158">Dodaj następujący wiersz na końcu nowej `Main` metody:</span><span class="sxs-lookup"><span data-stu-id="19468-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="19468-159">Tworzy listę liczb całkowitych i ustawia pierwsze dwie liczby całkowite na wartość 1.</span><span class="sxs-lookup"><span data-stu-id="19468-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="19468-160">Są to dwie pierwsze wartości *sekwencji Fibonacci*, sekwencja liczb.</span><span class="sxs-lookup"><span data-stu-id="19468-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="19468-161">Każdy kolejny numer Fibonacci można znaleźć, pobierając sumę poprzednich dwóch liczb.</span><span class="sxs-lookup"><span data-stu-id="19468-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="19468-162">Dodaj ten kod:</span><span class="sxs-lookup"><span data-stu-id="19468-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="19468-163">Zapisz plik i wpisz `dotnet run` , aby zobaczyć wyniki.</span><span class="sxs-lookup"><span data-stu-id="19468-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="19468-164">Aby skoncentrować się na tej sekcji, można skomentować kod, który wywołuje `WorkingWithStrings();` .</span><span class="sxs-lookup"><span data-stu-id="19468-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="19468-165">Po prostu umieść dwa `/` znaki przed wywołaniem podobnym do tego:  `// WorkingWithStrings();` .</span><span class="sxs-lookup"><span data-stu-id="19468-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="19468-166">Zadanie</span><span class="sxs-lookup"><span data-stu-id="19468-166">Challenge</span></span>

<span data-ttu-id="19468-167">Sprawdź, czy możesz połączyć niektóre koncepcje z tej i wcześniejszych lekcji.</span><span class="sxs-lookup"><span data-stu-id="19468-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="19468-168">Rozwiń elementy, które zostały już skompilowane z użyciem numerów Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="19468-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="19468-169">Spróbuj napisać kod w celu wygenerowania pierwszych 20 cyfr w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="19468-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="19468-170">(Jako wskazówkę 20 Fibonacci numer jest 6765).</span><span class="sxs-lookup"><span data-stu-id="19468-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="19468-171">Ukończenie wyzwania</span><span class="sxs-lookup"><span data-stu-id="19468-171">Complete challenge</span></span>

<span data-ttu-id="19468-172">Przykładowe rozwiązanie można zobaczyć, [przeglądając gotowy przykładowy kod w serwisie GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="19468-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span></span>

<span data-ttu-id="19468-173">Każda iteracja pętli polega na wykorzystaniu ostatnich dwóch liczb całkowitych na liście, sumowaniu ich i dodawania tej wartości do listy.</span><span class="sxs-lookup"><span data-stu-id="19468-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="19468-174">Pętla jest powtarzana do momentu dodania 20 elementów do listy.</span><span class="sxs-lookup"><span data-stu-id="19468-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="19468-175">Gratulacje, ukończono samouczek z listą.</span><span class="sxs-lookup"><span data-stu-id="19468-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="19468-176">Możesz przejść do samouczka [wprowadzenie do klas](introduction-to-classes.md) w Twoim środowisku programistycznym.</span><span class="sxs-lookup"><span data-stu-id="19468-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="19468-177">Aby dowiedzieć się więcej na temat pracy z `List` typem w artykule podstawowe informacje dotyczące platformy .NET, zobacz temat [kolekcje](../../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="19468-177">You can learn more about working with the `List` type in the .NET fundamentals article on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="19468-178">Zapoznaj się również z wieloma innymi typami kolekcji.</span><span class="sxs-lookup"><span data-stu-id="19468-178">You'll also learn about many other collection types.</span></span>
