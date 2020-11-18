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
# <a name="linq-overview"></a>LINQ — przegląd

Language-Integrated Query (LINQ) zapewnia możliwości zapytań na poziomie języka i interfejs API [funkcji wyższej kolejności](https://en.wikipedia.org/wiki/Higher-order_function) do języka C# i Visual Basic, które umożliwiają pisanie kodu deklaratywnego.

## <a name="language-level-query-syntax"></a>Składnia zapytania na poziomie języka

Jest to Składnia zapytania poziomu języka:

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

Jest to ten sam przykład przy użyciu `IEnumerable<T>` interfejsu API:

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a>LINQ jest wyraźne

Wyobraź sobie, że masz listę zwierząt domowych, ale chcesz ją przekonwertować na słownik, w którym możesz uzyskać dostęp do Pet bezpośrednio przez jego `RFID` wartość.

Jest to tradycyjny kod niezbędny:

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

Zamiarem za kod nie jest utworzenie nowego `Dictionary<int, Pet>` i dodanie go do niego za pośrednictwem pętli, dlatego konwersja istniejącej listy do słownika! LINQ zachowuje zamiar, w których sam kod nie jest.

Jest to równoważne wyrażenie LINQ:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

Kod przy użyciu LINQ jest cenny, ponieważ nawet pole Play między intencją a kodem, gdy jest to programista. Kolejną premią jest zwięzłości kodu. Załóżmy, że zmniejszasz duże fragmenty kodu bazy danych o 1/3 jak powyżej. Czy masz prawo do transakcji słodkiej?

## <a name="linq-providers-simplify-data-access"></a>Dostawcy LINQ upraszczają dostęp do danych

Aby uzyskać znaczący fragment oprogramowania na świecie, wszystko to koncentruje się na danych z niektórych źródeł (baz danych, JSON, XML itd.). Często obejmuje to uczenie nowego interfejsu API dla każdego źródła danych, co może być irytujące. LINQ upraszcza to dzięki abstrakcyjnym typowym elementom dostępu do danych do składni zapytań, która wygląda tak samo niezależnie od wybranego źródła danych.

Spowoduje to znalezienie wszystkich elementów XML o określonej wartości atrybutu:

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

Pisanie kodu do ręcznego przechodzenia dokumentu XML, aby to zadanie było znacznie trudniejsze.

Korzystanie z języka XML nie jest jedynym elementem, który można wykonywać za pomocą dostawców LINQ. [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) to dość bez systemu operacyjnego, Object-Relational MAPER (ORM) dla bazy danych serwera MSSQL. Biblioteka [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) zapewnia wydajną przechodzenie dokumentów JSON za pośrednictwem LINQ. Ponadto jeśli nie ma biblioteki, która robi to potrzebne, możesz również [napisać własnego dostawcę LINQ](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).

## <a name="reasons-to-use-the-query-syntax"></a>Przyczyny użycia składni zapytania

Dlaczego warto używać składni zapytania? Jest to pytanie, które często pojawia się. Po wykonaniu tych czynności Poniższy kod:

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

jest znacznie bardziej zwięzły niż:

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

Czy składnia interfejsu API jest bardziej zwięzła, aby wykonać składnię zapytania?

Nie. Składnia zapytania umożliwia użycie klauzuli **Let** , która umożliwia wprowadzenie i powiązanie zmiennej w zakresie wyrażenia, przy użyciu jej w kolejnych fragmentach wyrażenia. Odtwarzanie tego samego kodu tylko przy użyciu składni interfejsu API można wykonać, ale najprawdopodobniej prowadzi to do kodu, który trudno odczytać.

W związku z tym begs pytanie, **czy wystarczy użyć składni zapytania?**

Odpowiedź na to pytanie ma **wartość tak** , jeśli:

- Istniejąca baza kodu używa już składni zapytania.
- Należy określić zakres zmiennych w zapytaniach ze względu na złożoność.
- Wolisz składnię zapytania i nie będzie ona przeszkadzać w kodzie bazowym.

Odpowiedź na to pytanie **nie** dotyczy, jeśli...

- Istniejąca baza kodu używa już składni interfejsu API
- Nie ma potrzeby określania zakresu zmiennych w zapytaniach
- Wolisz składnię interfejsu API i nie będzie ona przeszkadzać w kodzie bazowym

## <a name="essential-linq"></a>Podstawowe LINQ

Aby zapoznać się z prawdziwie obszerną listą przykładów LINQ, zobacz [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/).

Poniższe przykłady przedstawiają szybką demonstrację niektórych najważniejszych fragmentów LINQ. Ta funkcja nie jest kompletna, ponieważ składnik LINQ oferuje więcej funkcji niż przedstawiono tutaj.

### <a name="the-bread-and-butter---where-select-and-aggregate"></a>Chleb i masło `Where` ,, `Select` i `Aggregate`

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

### <a name="flattening-a-list-of-lists"></a>Spłaszczanie listy list

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a>Złożenie między dwoma zestawami (z niestandardowym komparatorem)

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

### <a name="intersection-between-two-sets"></a>Część wspólna między dwoma zestawami

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

### <a name="ordering"></a>Zamawianie

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

### <a name="equality-of-instance-properties"></a>Równość właściwości wystąpienia

Na koniec bardziej zaawansowaną próbkę: określenie, czy wartości właściwości dwóch wystąpień tego samego typu są równe (zapożyczone i zmodyfikowane z [tego StackOverflow post](https://stackoverflow.com/a/844855)):

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

## <a name="plinq"></a>PLINQ

PLINQ lub Parallel LINQ jest aparatem wykonywania równoległym dla wyrażeń LINQ. Inaczej mówiąc, regularne wyrażenie LINQ może być równolegle równoległe do dowolnej liczby wątków. Jest to realizowane za pośrednictwem wywołania `AsParallel()` poprzedzającego wyrażenie.

Rozważ następujące źródła:

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

Ten kod podzieli się na `facebookUsers` poszczególne wątki systemu w miarę potrzeb, sumuje całkowitą liczbę polubień w każdym wątku równolegle, sumuje wyniki obliczone przez poszczególne wątki i projektu, które powodują powstanie ciągu znaków.

W formularzu diagramu:

![Diagram PLINQ](media/index/plinq-diagram.png)

Działania równoległego zadania powiązane z PROCESORem, które mogą być łatwo wyrażone za pośrednictwem LINQ (innymi słowy, są czystymi funkcjami i nie mają efektów ubocznych) to doskonały kandydat do PLINQ. W przypadku zadań _, które mają_ efekt uboczny, należy rozważyć użycie [biblioteki zadań równoległych](../parallel-programming/task-parallel-library-tpl.md).

## <a name="more-resources"></a>Dodatkowe zasoby

* [Przykłady dla LINQ 101](/samples/dotnet/try-samples/101-linq-samples/)
* [LINQPad](https://www.linqpad.net/), środowisko plac zabaw i aparat zapytań bazy danych dla języka C#/F #/Visual Basic
* [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/)— książka elektroniczna do uczenia się, jak jest implementowane LINQ-to-Objects
