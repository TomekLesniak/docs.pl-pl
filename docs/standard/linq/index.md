---
title: LINQ — Omówienie — .NET
description: Language-Integrated Query (LINQ) zapewnia możliwości zapytań na poziomie języka i interfejs API funkcji wyższej kolejności do języka C# i Visual Basic, które umożliwiają pisanie kodu deklaratywnego.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
dev_langs:
- csharp
- vb
ms.openlocfilehash: ed78082c97511a8dbcc48d413a75a46c9da906a9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825835"
---
# <a name="linq-overview"></a><span data-ttu-id="b2865-103">LINQ — przegląd</span><span class="sxs-lookup"><span data-stu-id="b2865-103">LINQ overview</span></span>

<span data-ttu-id="b2865-104">Language-Integrated Query (LINQ) zapewnia możliwości zapytań na poziomie języka i interfejs API [funkcji wyższej kolejności](https://en.wikipedia.org/wiki/Higher-order_function) do języka C# i Visual Basic, które umożliwiają pisanie kodu deklaratywnego.</span><span class="sxs-lookup"><span data-stu-id="b2865-104">Language-Integrated Query (LINQ) provides language-level querying capabilities, and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic, that enable you to write expressive declarative code.</span></span>

## <a name="language-level-query-syntax"></a><span data-ttu-id="b2865-105">Składnia zapytania na poziomie języka</span><span class="sxs-lookup"><span data-stu-id="b2865-105">Language-level query syntax</span></span>

<span data-ttu-id="b2865-106">Jest to Składnia zapytania poziomu języka:</span><span class="sxs-lookup"><span data-stu-id="b2865-106">This is the language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

```vb
Dim linqExperts = From p in programmers
                  Where p.IsNewToLINQ
                  Select New LINQExpert(p)
```

<span data-ttu-id="b2865-107">Jest to ten sam przykład przy użyciu `IEnumerable<T>` interfejsu API:</span><span class="sxs-lookup"><span data-stu-id="b2865-107">This is the same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="b2865-108">LINQ jest wyraźne</span><span class="sxs-lookup"><span data-stu-id="b2865-108">LINQ is expressive</span></span>

<span data-ttu-id="b2865-109">Wyobraź sobie, że masz listę zwierząt domowych, ale chcesz ją przekonwertować na słownik, w którym możesz uzyskać dostęp do Pet bezpośrednio przez jego `RFID` wartość.</span><span class="sxs-lookup"><span data-stu-id="b2865-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="b2865-110">Jest to tradycyjny kod niezbędny:</span><span class="sxs-lookup"><span data-stu-id="b2865-110">This is traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

<span data-ttu-id="b2865-111">Zamiarem za kod nie jest utworzenie nowego `Dictionary<int, Pet>` i dodanie go do niego za pośrednictwem pętli, dlatego konwersja istniejącej listy do słownika!</span><span class="sxs-lookup"><span data-stu-id="b2865-111">The intention behind the code isn't to create a new `Dictionary<int, Pet>` and add to it via a loop, it's to convert an existing list into a dictionary!</span></span> <span data-ttu-id="b2865-112">LINQ zachowuje zamiar, w których sam kod nie jest.</span><span class="sxs-lookup"><span data-stu-id="b2865-112">LINQ preserves the intention whereas the imperative code doesn't.</span></span>

<span data-ttu-id="b2865-113">Jest to równoważne wyrażenie LINQ:</span><span class="sxs-lookup"><span data-stu-id="b2865-113">This is the equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="b2865-114">Kod przy użyciu LINQ jest cenny, ponieważ nawet pole Play między intencją a kodem, gdy jest to programista.</span><span class="sxs-lookup"><span data-stu-id="b2865-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="b2865-115">Kolejną premią jest zwięzłości kodu.</span><span class="sxs-lookup"><span data-stu-id="b2865-115">Another bonus is code brevity.</span></span> <span data-ttu-id="b2865-116">Załóżmy, że zmniejszasz duże fragmenty kodu bazy danych o 1/3 jak powyżej.</span><span class="sxs-lookup"><span data-stu-id="b2865-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="b2865-117">Czy masz prawo do transakcji słodkiej?</span><span class="sxs-lookup"><span data-stu-id="b2865-117">Sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="b2865-118">Dostawcy LINQ upraszczają dostęp do danych</span><span class="sxs-lookup"><span data-stu-id="b2865-118">LINQ providers simplify data access</span></span>

<span data-ttu-id="b2865-119">Aby uzyskać znaczący fragment oprogramowania na świecie, wszystko to koncentruje się na danych z niektórych źródeł (baz danych, JSON, XML itd.).</span><span class="sxs-lookup"><span data-stu-id="b2865-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, and so on).</span></span> <span data-ttu-id="b2865-120">Często obejmuje to uczenie nowego interfejsu API dla każdego źródła danych, co może być irytujące.</span><span class="sxs-lookup"><span data-stu-id="b2865-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="b2865-121">LINQ upraszcza to dzięki abstrakcyjnym typowym elementom dostępu do danych do składni zapytań, która wygląda tak samo niezależnie od wybranego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b2865-121">LINQ simplifies this by abstracting common elements of data access into a query syntax that looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="b2865-122">Spowoduje to znalezienie wszystkich elementów XML o określonej wartości atrybutu:</span><span class="sxs-lookup"><span data-stu-id="b2865-122">This finds all XML elements with a specific attribute value:</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function
```

<span data-ttu-id="b2865-123">Pisanie kodu do ręcznego przechodzenia dokumentu XML, aby to zadanie było znacznie trudniejsze.</span><span class="sxs-lookup"><span data-stu-id="b2865-123">Writing code to manually traverse the XML document to do this task would be far more challenging.</span></span>

<span data-ttu-id="b2865-124">Korzystanie z języka XML nie jest jedynym elementem, który można wykonywać za pomocą dostawców LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2865-124">Interacting with XML isn't the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="b2865-125">[LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) to dość bez systemu operacyjnego, Object-Relational MAPER (ORM) dla bazy danych serwera MSSQL.</span><span class="sxs-lookup"><span data-stu-id="b2865-125">[Linq to SQL](../../framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="b2865-126">Biblioteka [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) zapewnia wydajną przechodzenie dokumentów JSON za pośrednictwem LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2865-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="b2865-127">Ponadto jeśli nie ma biblioteki, która robi to potrzebne, możesz również [napisać własnego dostawcę LINQ](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="b2865-127">Furthermore, if there isn't a library that does what you need, you can also [write your own LINQ Provider](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="reasons-to-use-the-query-syntax"></a><span data-ttu-id="b2865-128">Przyczyny użycia składni zapytania</span><span class="sxs-lookup"><span data-stu-id="b2865-128">Reasons to use the query syntax</span></span>

<span data-ttu-id="b2865-129">Dlaczego warto używać składni zapytania?</span><span class="sxs-lookup"><span data-stu-id="b2865-129">Why use query syntax?</span></span> <span data-ttu-id="b2865-130">Jest to pytanie, które często pojawia się.</span><span class="sxs-lookup"><span data-stu-id="b2865-130">This is a question that often comes up.</span></span> <span data-ttu-id="b2865-131">Po wykonaniu tych czynności Poniższy kod:</span><span class="sxs-lookup"><span data-stu-id="b2865-131">After all, the following code:</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="b2865-132">jest znacznie bardziej zwięzły niż:</span><span class="sxs-lookup"><span data-stu-id="b2865-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

```vb
Dim filteredItems = From item In myItems
                    Where item.Foo
                    Select item
```

<span data-ttu-id="b2865-133">Czy składnia interfejsu API jest bardziej zwięzła, aby wykonać składnię zapytania?</span><span class="sxs-lookup"><span data-stu-id="b2865-133">Isn't the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="b2865-134">Nie.</span><span class="sxs-lookup"><span data-stu-id="b2865-134">No.</span></span> <span data-ttu-id="b2865-135">Składnia zapytania umożliwia użycie klauzuli **Let** , która umożliwia wprowadzenie i powiązanie zmiennej w zakresie wyrażenia, przy użyciu jej w kolejnych fragmentach wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b2865-135">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="b2865-136">Odtwarzanie tego samego kodu tylko przy użyciu składni interfejsu API można wykonać, ale najprawdopodobniej prowadzi to do kodu, który trudno odczytać.</span><span class="sxs-lookup"><span data-stu-id="b2865-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code that's hard to read.</span></span>

<span data-ttu-id="b2865-137">W związku z tym begs pytanie, **czy wystarczy użyć składni zapytania?**</span><span class="sxs-lookup"><span data-stu-id="b2865-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="b2865-138">Odpowiedź na to pytanie ma **wartość tak** , jeśli:</span><span class="sxs-lookup"><span data-stu-id="b2865-138">The answer to this question is **yes** if:</span></span>

- <span data-ttu-id="b2865-139">Istniejąca baza kodu używa już składni zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2865-139">Your existing codebase already uses the query syntax.</span></span>
- <span data-ttu-id="b2865-140">Należy określić zakres zmiennych w zapytaniach ze względu na złożoność.</span><span class="sxs-lookup"><span data-stu-id="b2865-140">You need to scope variables within your queries because of complexity.</span></span>
- <span data-ttu-id="b2865-141">Wolisz składnię zapytania i nie będzie ona przeszkadzać w kodzie bazowym.</span><span class="sxs-lookup"><span data-stu-id="b2865-141">You prefer the query syntax and it won't distract from your codebase.</span></span>

<span data-ttu-id="b2865-142">Odpowiedź na to pytanie **nie** dotyczy, jeśli...</span><span class="sxs-lookup"><span data-stu-id="b2865-142">The answer to this question is **no** if...</span></span>

- <span data-ttu-id="b2865-143">Istniejąca baza kodu używa już składni interfejsu API</span><span class="sxs-lookup"><span data-stu-id="b2865-143">Your existing codebase already uses the API syntax</span></span>
- <span data-ttu-id="b2865-144">Nie ma potrzeby określania zakresu zmiennych w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="b2865-144">You have no need to scope variables within your queries</span></span>
- <span data-ttu-id="b2865-145">Wolisz składnię interfejsu API i nie będzie ona przeszkadzać w kodzie bazowym</span><span class="sxs-lookup"><span data-stu-id="b2865-145">You prefer the API syntax and it won't distract from your codebase</span></span>

## <a name="essential-linq"></a><span data-ttu-id="b2865-146">Podstawowe LINQ</span><span class="sxs-lookup"><span data-stu-id="b2865-146">Essential LINQ</span></span>

<span data-ttu-id="b2865-147">Aby zapoznać się z prawdziwie obszerną listą przykładów LINQ, zobacz [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/).</span><span class="sxs-lookup"><span data-stu-id="b2865-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/).</span></span>

<span data-ttu-id="b2865-148">Poniższe przykłady przedstawiają szybką demonstrację niektórych najważniejszych fragmentów LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2865-148">The following examples are a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="b2865-149">Ta funkcja nie jest kompletna, ponieważ składnik LINQ oferuje więcej funkcji niż przedstawiono tutaj.</span><span class="sxs-lookup"><span data-stu-id="b2865-149">This is in no way comprehensive, as LINQ provides more functionality than what is showcased here.</span></span>

### <a name="the-bread-and-butter---where-select-and-aggregate"></a><span data-ttu-id="b2865-150">Chleb i masło `Where` ,, `Select` i `Aggregate`</span><span class="sxs-lookup"><span data-stu-id="b2865-150">The bread and butter - `Where`, `Select`, and `Aggregate`</span></span>

```csharp
// Filtering a list.
var germanShepherds = dogs.Where(dog => dog.Breed == DogBreed.GermanShepherd);

// Using the query syntax.
var queryGermanShepherds = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepherd
                          select dog;

// Mapping a list from type A to type B.
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax.
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings.
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

```vb
' Filtering a list.
Dim germanShepherds = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepherd)

' Using the query syntax.
Dim queryGermanShepherds = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepherd
                          Select dog

' Mapping a list from type A to type B.
Dim cats = dogs.Select(Function(dog) dog.TurnIntoACat())

' Using the query syntax.
Dim queryCats = From dog In dogs
                Select dog.TurnIntoACat()

' Summing the lengths of a set of strings.
Dim seed As Integer = 0
Dim sumOfStrings As Integer = strings.Aggregate(seed, Function(s1, s2) s1.Length + s2.Length)
```

### <a name="flattening-a-list-of-lists"></a><span data-ttu-id="b2865-151">Spłaszczanie listy list</span><span class="sxs-lookup"><span data-stu-id="b2865-151">Flattening a list of lists</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a><span data-ttu-id="b2865-152">Złożenie między dwoma zestawami (z niestandardowym komparatorem)</span><span class="sxs-lookup"><span data-stu-id="b2865-152">Union between two sets (with custom comparator)</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // Default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}
...

// Gets all the short-haired dogs between two different kennels.
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());

```

```vb
Public Class DogHairLengthComparer
  Inherits IEqualityComparer(Of Dog)

  Public Function Equals(a As Dog,b As Dog) As Boolean
      If a Is Nothing AndAlso b Is Nothing Then
          Return True
      ElseIf (a Is Nothing AndAlso b IsNot Nothing) OrElse (a IsNot Nothing AndAlso b Is Nothing) Then
          Return False
      Else
          Return a.HairLengthType = b.HairLengthType
      End If
  End Function

  Public Function GetHashCode(d As Dog) As Integer
      ' Default hashcode is enough here, as these are simple objects.
      Return d.GetHashCode()
  End Function
End Class

...

' Gets all the short-haired dogs between two different kennels.
Dim allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, New DogHairLengthComparer())
```

### <a name="intersection-between-two-sets"></a><span data-ttu-id="b2865-153">Część wspólna między dwoma zestawami</span><span class="sxs-lookup"><span data-stu-id="b2865-153">Intersection between two sets</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

```vb
' Gets the volunteers who spend share time with two humane societies.
Dim volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     New VolunteerTimeComparer())
```

### <a name="ordering"></a><span data-ttu-id="b2865-154">Zamawianie</span><span class="sxs-lookup"><span data-stu-id="b2865-154">Ordering</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

```vb
' Get driving directions, ordering by if it's toll-free before estimated driving time.
Dim results = DirectionsProcessor.GetDirections(start, end).
                OrderBy(Function(direction) direction.HasNoTolls).
                ThenBy(Function(direction) direction.EstimatedTime)
```

### <a name="equality-of-instance-properties"></a><span data-ttu-id="b2865-155">Równość właściwości wystąpienia</span><span class="sxs-lookup"><span data-stu-id="b2865-155">Equality of instance properties</span></span>

<span data-ttu-id="b2865-156">Na koniec bardziej zaawansowaną próbkę: określenie, czy wartości właściwości dwóch wystąpień tego samego typu są równe (zapożyczone i zmodyfikowane z [tego StackOverflow post](https://stackoverflow.com/a/844855)):</span><span class="sxs-lookup"><span data-stu-id="b2865-156">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self == null || to == null)
    {
        return self == to;
    }

    // Selects the properties which have unequal values into a sequence of those properties.
    var unequalProperties = from property in typeof(T).GetProperties(BindingFlags.Public | BindingFlags.Instance)
                            where !ignore.Contains(property.Name)
                            let selfValue = property.GetValue(self, null)
                            let toValue = property.GetValue(to, null)
                            where !Equals(selfValue, toValue)
                            select property;
    return !unequalProperties.Any();
}
```

```vb
<System.Runtime.CompilerServices.Extension()>
Public Function PublicInstancePropertiesEqual(Of T As Class)(self As T, [to] As T, ParamArray ignore As String()) As Boolean
    If self Is Nothing OrElse [to] Is Nothing Then
        Return self Is [to]
    End If

    ' Selects the properties which have unequal values into a sequence of those properties.
    Dim unequalProperties = From [property] In GetType(T).GetProperties(BindingFlags.Public Or BindingFlags.Instance)
                            Where Not ignore.Contains([property].Name)
                            Let selfValue = [property].GetValue(self, Nothing)
                            Let toValue = [property].GetValue([to], Nothing)
                            Where Not Equals(selfValue, toValue) Select [property]
    Return Not unequalProperties.Any()
End Function
```

## <a name="plinq"></a><span data-ttu-id="b2865-157">PLINQ</span><span class="sxs-lookup"><span data-stu-id="b2865-157">PLINQ</span></span>

<span data-ttu-id="b2865-158">PLINQ lub Parallel LINQ jest aparatem wykonywania równoległym dla wyrażeń LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2865-158">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="b2865-159">Inaczej mówiąc, regularne wyrażenie LINQ może być równolegle równoległe do dowolnej liczby wątków.</span><span class="sxs-lookup"><span data-stu-id="b2865-159">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="b2865-160">Jest to realizowane za pośrednictwem wywołania `AsParallel()` poprzedzającego wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="b2865-160">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="b2865-161">Rozważ następujące źródła:</span><span class="sxs-lookup"><span data-stu-id="b2865-161">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

```vb
Public Shared GetAllFacebookUserLikesMessage(facebookUsers As IEnumerable(Of FacebookUser)) As String
{
    Dim seed As UInt64 = 0

    Dim threadAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim threadResultAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim resultSelector As Func(Of Uint64, string) = Function(total) $"Facebook has {total} likes!"

    Return facebookUsers.AsParallel().
                        Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector)
}
```

<span data-ttu-id="b2865-162">Ten kod podzieli się na `facebookUsers` poszczególne wątki systemu w miarę potrzeb, sumuje całkowitą liczbę polubień w każdym wątku równolegle, sumuje wyniki obliczone przez poszczególne wątki i projektu, które powodują powstanie ciągu znaków.</span><span class="sxs-lookup"><span data-stu-id="b2865-162">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="b2865-163">W formularzu diagramu:</span><span class="sxs-lookup"><span data-stu-id="b2865-163">In diagram form:</span></span>

![Diagram PLINQ](media/index/plinq-diagram.png)

<span data-ttu-id="b2865-165">Działania równoległego zadania powiązane z PROCESORem, które mogą być łatwo wyrażone za pośrednictwem LINQ (innymi słowy, są czystymi funkcjami i nie mają efektów ubocznych) to doskonały kandydat do PLINQ.</span><span class="sxs-lookup"><span data-stu-id="b2865-165">Parallelizable CPU-bound jobs that can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="b2865-166">W przypadku zadań _, które mają_ efekt uboczny, należy rozważyć użycie [biblioteki zadań równoległych](../parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="b2865-166">For jobs that _do_ have a side effect, consider using the [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="b2865-167">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b2865-167">More resources</span></span>

* [<span data-ttu-id="b2865-168">Przykłady dla LINQ 101</span><span class="sxs-lookup"><span data-stu-id="b2865-168">101 LINQ Samples</span></span>](/samples/dotnet/try-samples/101-linq-samples/)
* <span data-ttu-id="b2865-169">[LINQPad](https://www.linqpad.net/), środowisko plac zabaw i aparat zapytań bazy danych dla języka C#/F #/Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2865-169">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="b2865-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/)— książka elektroniczna do uczenia się, jak jest implementowane LINQ-to-Objects</span><span class="sxs-lookup"><span data-stu-id="b2865-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
