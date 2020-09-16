---
title: Typy ogólne (ogólne) — Omówienie
description: Dowiedz się, w jaki sposób typy ogólne działają jako szablony kodu, które umożliwiają definiowanie bezpiecznych dla typu struktur danych bez przekazywania ich do rzeczywistego typu danych.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 5f6e84e23b5bcdcb3dcd742823d83728fb43d195
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557947"
---
# <a name="generic-types-overview"></a><span data-ttu-id="44624-103">Przegląd typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="44624-103">Generic types overview</span></span>

<span data-ttu-id="44624-104">Deweloperzy używają typów ogólnych przez cały czas w programie .NET, niezależnie od tego, czy jest to jawnie, czy niejawnie.</span><span class="sxs-lookup"><span data-stu-id="44624-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="44624-105">Kiedy używasz LINQ w programie .NET, czy wiesz, że pracujesz z <xref:System.Collections.Generic.IEnumerable%601> ?</span><span class="sxs-lookup"><span data-stu-id="44624-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="44624-106">Lub jeśli kiedykolwiek zdarzyło Ci się korzystać z przykładu online "ogólnego repozytorium" do nawiązywania komunikacji z bazami danych przy użyciu Entity Framework, zobaczysz, że większość metod zwraca `IQueryable<T>` ?</span><span class="sxs-lookup"><span data-stu-id="44624-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return `IQueryable<T>`?</span></span> <span data-ttu-id="44624-107">Być może zastanawiasz się, co znajduje się w tych przykładach i dlaczego znajduje się **w tym miejscu** .</span><span class="sxs-lookup"><span data-stu-id="44624-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="44624-108">Po raz pierwszy wprowadzona w .NET Framework 2,0, typy ogólne są zasadniczo "szablonem kodu", dzięki czemu deweloperzy mogą definiować [bezpieczne dla typów](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) struktury danych bez przekazywania ich do rzeczywistego typu danych.</span><span class="sxs-lookup"><span data-stu-id="44624-108">First introduced in the .NET Framework 2.0, generics are essentially a "code template" that allows developers to define [type-safe](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="44624-109">Na przykład <xref:System.Collections.Generic.List%601> to [Ogólna kolekcja](xref:System.Collections.Generic) , która może być zadeklarowana i używana z dowolnym typem, takim jak `List<int>` , `List<string>` lub `List<Person>` .</span><span class="sxs-lookup"><span data-stu-id="44624-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="44624-110">Aby zrozumieć, dlaczego typy ogólne są przydatne, przyjrzyjmy się określonej klasie przed i po dodaniu typów ogólnych: <xref:System.Collections.ArrayList> .</span><span class="sxs-lookup"><span data-stu-id="44624-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="44624-111">W .NET Framework 1,0 `ArrayList` elementy były typu <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="44624-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="44624-112">Każdy element dodany do kolekcji został dyskretnie przekonwertowany na `Object` .</span><span class="sxs-lookup"><span data-stu-id="44624-112">Any element added to the collection was silently converted into an `Object`.</span></span> <span data-ttu-id="44624-113">Taka sytuacja miałaby miejsce podczas odczytywania elementów z listy.</span><span class="sxs-lookup"><span data-stu-id="44624-113">The same would happen when reading elements from the list.</span></span> <span data-ttu-id="44624-114">Ten proces jest nazywany [opakowaniem i rozpakowywaniem](../csharp/programming-guide/types/boxing-and-unboxing.md)i ma wpływ na wydajność.</span><span class="sxs-lookup"><span data-stu-id="44624-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="44624-115">Poza wydajnością nie ma jednak możliwości określenia typu danych na liście w czasie kompilacji, co sprawia, że jest to niedelikatny kod.</span><span class="sxs-lookup"><span data-stu-id="44624-115">Aside from performance, however, there's no way to determine the type of data in the list at compile time, which makes for some fragile code.</span></span> <span data-ttu-id="44624-116">Typy ogólne rozwiązują ten problem przez zdefiniowanie typu danych, które będą zawierać każde wystąpienie listy.</span><span class="sxs-lookup"><span data-stu-id="44624-116">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="44624-117">Na przykład można dodawać tylko liczby całkowite do `List<int>` i dodawać tylko osoby do `List<Person>` .</span><span class="sxs-lookup"><span data-stu-id="44624-117">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="44624-118">Typy ogólne są również dostępne w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="44624-118">Generics are also available at run time.</span></span> <span data-ttu-id="44624-119">Środowisko uruchomieniowe wie, jakiego typu struktura danych używasz i może być bardziej wydajnie przechowywana w pamięci.</span><span class="sxs-lookup"><span data-stu-id="44624-119">The runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="44624-120">Poniższy przykład jest małym programem, który ilustruje efektywność znajomości typu struktury danych w czasie wykonywania:</span><span class="sxs-lookup"><span data-stu-id="44624-120">The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="44624-121">Ten program generuje dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="44624-121">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="44624-122">W pierwszej kolejności można zauważyć, że sortowanie listy ogólnej jest znacznie szybsze niż sortowanie listy nieogólnej.</span><span class="sxs-lookup"><span data-stu-id="44624-122">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="44624-123">Można również zauważyć, że typ listy ogólnej to DISTINCT ([System. Int32]), podczas gdy typ dla listy nieogólnej jest uogólniony.</span><span class="sxs-lookup"><span data-stu-id="44624-123">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="44624-124">Ponieważ środowisko uruchomieniowe wie, że ogólny `List<int>` jest typu <xref:System.Int32> , może przechowywać elementy listy w źródłowej tablicy liczb całkowitych w pamięci, podczas gdy nieogólny `ArrayList` musi rzutować każdy element listy na obiekt.</span><span class="sxs-lookup"><span data-stu-id="44624-124">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory, while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="44624-125">Jak pokazano w tym przykładzie, dodatkowe rzuty zajmują czas i spowalniają sortowanie listy.</span><span class="sxs-lookup"><span data-stu-id="44624-125">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="44624-126">Dodatkową zaletą środowiska uruchomieniowego, wiedząc, że typ ogólny jest lepszym rozwiązaniem debugowania.</span><span class="sxs-lookup"><span data-stu-id="44624-126">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="44624-127">Gdy debugujesz ogólne w języku C#, wiesz, jaki typ każdy element znajduje się w strukturze danych.</span><span class="sxs-lookup"><span data-stu-id="44624-127">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="44624-128">Bez typów ogólnych nie ma żadnego pomysłu na to, co typ każdy element był.</span><span class="sxs-lookup"><span data-stu-id="44624-128">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="44624-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="44624-129">See also</span></span>

- [<span data-ttu-id="44624-130">Przewodnik programowania w języku C# — typy ogólne</span><span class="sxs-lookup"><span data-stu-id="44624-130">C# Programming Guide - Generics</span></span>](../csharp/programming-guide/generics/index.md)
