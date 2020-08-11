---
title: System. Delegate i `delegate` słowo kluczowe
description: Dowiedz się więcej na temat klas w programie .NET, które obsługują delegatów i jak te są mapowane na słowo kluczowe "Delegate".
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 9df8ad68f6bfa62863ee047875b6419fc81ad779
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062468"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a>System. Delegate i `delegate` słowo kluczowe

[Poprzednie](delegates-overview.md)

W tym artykule opisano klasy w programie .NET, które obsługują delegatów i jak te są mapowane na `delegate` słowo kluczowe.

## <a name="define-delegate-types"></a>Definiowanie typów delegatów

Zacznijmy od słowa kluczowego "Delegate", ponieważ jest to przede wszystkim, czego będziesz używać podczas pracy z delegatami. Kod generowany przez kompilator, gdy użycie `delegate` słowa kluczowego zostanie zmapowane na wywołania metody, które wywołują elementy członkowskie <xref:System.Delegate> <xref:System.MulticastDelegate> klas i.

Należy zdefiniować typ delegata przy użyciu składni podobnej do definiowania sygnatury metody. Wystarczy dodać `delegate` słowo kluczowe do definicji.

Kontynuujmy używanie metody list. Sort () jako przykładu. Pierwszym krokiem jest utworzenie typu dla delegata porównania:

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

Kompilator generuje klasę pochodną, `System.Delegate` która jest zgodna z używanym podpisem (w tym przypadku metoda zwraca liczbę całkowitą i ma dwa argumenty). Typ tego delegata to `Comparison` . `Comparison`Typ delegata jest typem ogólnym. Aby uzyskać szczegółowe informacje na temat typów ogólnych, zobacz [tutaj](programming-guide/generics/index.md).

Zauważ, że składnia może wyglądać tak, jakby deklaruje zmienną, ale faktycznie deklaruje *Typ*. Można definiować typy delegatów wewnątrz klas, bezpośrednio w przestrzeniach nazw, a nawet w globalnej przestrzeni nazw.

> [!NOTE]
> Deklarowanie typów delegatów (lub innych typów) bezpośrednio w globalnej przestrzeni nazw nie jest zalecane.

Kompilator generuje również procedury obsługi dodawania i usuwania dla tego nowego typu, tak aby klienci tej klasy mogli dodawać i usuwać metody z listy wywołań wystąpienia. Kompilator wymusza, że podpis metody dodawanej lub usuwanej jest zgodny z podpisem używanym podczas deklarowania metody.

## <a name="declare-instances-of-delegates"></a>Deklarowanie wystąpień delegatów

Po zdefiniowaniu delegata można utworzyć wystąpienie tego typu.
Podobnie jak w przypadku wszystkich zmiennych w języku C#, nie można zadeklarować wystąpień delegatów bezpośrednio w przestrzeni nazw lub w globalnej przestrzeni nazw.

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

Typ zmiennej to `Comparison<T>` , zdefiniowany wcześniej typ delegata. Nazwa zmiennej to `comparator` .

 Ten fragment kodu jest zadeklarowany jako zmienna członkowska wewnątrz klasy. Można również zadeklarować zmienne delegatów, które są zmiennymi lokalnymi lub argumenty metod.

## <a name="invoke-delegates"></a>Wywołaj delegatów

Metody, które znajdują się na liście wywołań delegata, są wywoływane przez wywołanie tego delegata. Wewnątrz `Sort()` metody kod wywoła metodę porównania, aby określić, która kolejność umieszczania obiektów:

```csharp
int result = comparator(left, right);
```

W wierszu powyżej kod *wywołuje* metodę dołączoną do delegata.
Zmienna jest traktowana jako nazwa metody i wywołuje ją przy użyciu standardowej składni wywołania metody.

Ten wiersz kodu powoduje niebezpieczne założenie: nie ma gwarancji, że element docelowy został dodany do delegata. Jeśli nie dołączono żadnych elementów docelowych, wiersz powyżej mógłby `NullReferenceException` zostać zgłoszony. Idiomy używany do rozwiązywania tego problemu są bardziej skomplikowane niż proste sprawdzenie wartości null i zostały omówione w dalszej części tej [serii](delegates-patterns.md).

## <a name="assign-add-and-remove-invocation-targets"></a>Przypisywanie, Dodawanie i usuwanie elementów docelowych wywołań

Jest to sposób definiowania typu delegata oraz sposobu deklarowania i wywołania delegatów.

Deweloperzy, którzy chcą korzystać z `List.Sort()` metody, muszą zdefiniować metodę, której sygnatura jest zgodna z definicją typu delegata, i przypisać ją do delegata używanego przez metodę Sort. To przypisanie dodaje metodę do listy wywołań tego obiektu delegowanego.

Załóżmy, że chcemy sortować listę ciągów według ich długości. Funkcja porównania może być następująca:

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

Metoda jest zadeklarowana jako Metoda prywatna. To dobrze. Nie można chcieć, aby ta metoda była częścią interfejsu publicznego. Nadal może być używana jako metoda porównania w przypadku dołączenia do delegata. Kod wywołujący będzie miał tę metodę dołączoną do listy docelowej obiektu delegowanego i może uzyskać do niej dostęp za pomocą tego delegata.

Ta relacja jest tworzona przez przekazanie tej metody do `List.Sort()` metody:

```csharp
phrases.Sort(CompareLength);
```

Zauważ, że nazwa metody jest używana, bez nawiasów. Użycie metody jako argumentu instruuje kompilator, aby przekonwertował odwołanie do metody na odwołanie, które może być użyte jako obiekt docelowy wywołania delegata i dołączyć tę metodę jako obiekt docelowy wywołania.

Można było również jawnie, deklarując zmienną typu `Comparison<string>` i wykonując przypisanie:

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

W używanym miejscu, gdzie Metoda używana jako obiekt docelowy delegata jest małą metodą, często jest używana składnia [wyrażenia lambda](language-reference/operators/lambda-expressions.md) do wykonania przypisania:

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

Użycie wyrażeń lambda dla obiektów docelowych delegatów zostało omówione w [dalszej części](delegates-patterns.md).

Przykład Sort () zazwyczaj dołącza jedną metodę docelową do delegata. Obiekty delegatów obsługują jednak listy wywołań, które mają wiele metod docelowych dołączonych do obiektu delegowanego.

## <a name="delegate-and-multicastdelegate-classes"></a>Klasy delegatów i MulticastDelegate

Opisana powyżej obsługa języka udostępnia funkcje i pomoc techniczną, które zwykle muszą współpracować z delegatami. Te funkcje są oparte na dwóch klasach w .NET Core Framework: <xref:System.Delegate> i <xref:System.MulticastDelegate> .

`System.Delegate`Klasy i jej pojedynczej podklasy bezpośredniej, `System.MulticastDelegate` ,,,, zapewniają obsługę struktury do tworzenia delegatów, rejestrowania metod jako obiektów docelowych delegatów i wywoływania wszystkich metod, które są zarejestrowane jako obiekt docelowy delegata.

W interesującej `System.Delegate` klasie i `System.MulticastDelegate` nie są sami typami delegatów. Zapewniają one podstawę dla wszystkich określonych typów delegatów. Ten sam proces projektowania języka nie może zadeklarować klasy, która dziedziczy z `Delegate` lub `MulticastDelegate` . Reguły języka C# zabraniają tego.

Zamiast tego kompilator języka C# tworzy wystąpienia klasy pochodnej `MulticastDelegate` przy użyciu słowa kluczowego języka c# do deklarowania typów delegatów.

Ten projekt zawiera elementy główne w pierwszej wersji języka C# i .NET. Jednym z celów zespołu projektowego jest upewnienie się, że język wymusza bezpieczeństwo typów podczas korzystania z delegatów. Ma to na celu zapewnienie, że Delegaty zostały wywołane z odpowiednim typem i liczbą argumentów. I, że każdy typ zwracany został prawidłowo wskazany w czasie kompilacji. Delegaty były częścią wersji 1,0 .NET, która była wcześniejsza niż ogólna.

Najlepszym sposobem wymuszenia zapewnienia bezpieczeństwa tego typu był kompilator w celu utworzenia konkretnych klas delegatów, które reprezentują używany podpis metody.

Mimo że nie można bezpośrednio tworzyć klas pochodnych, należy użyć metod zdefiniowanych dla tych klas. Przejdźmy do najpopularniejszych metod, które będą używane podczas pracy z delegatami.

Pierwszy z najważniejszych faktów, z których Pamiętaj, że każdy delegat, z którym pracujesz, pochodzi od `MulticastDelegate` . Delegat multiemisji oznacza, że można wywołać więcej niż jeden obiekt docelowy metody podczas wywoływania za pośrednictwem delegata. Oryginalny projekt uwzględniał rozróżnienie między delegatami, w których można dołączać i wywoływać tylko jedną metodę docelową, oraz delegatów, gdzie można dołączać i wywoływać wiele metod docelowych. Takie rozróżnienie okazało się mniej użyteczne w rzeczywistości niż pierwotnie przemyślane. Dwie różne klasy zostały już utworzone i zostały w strukturze od momentu jego początkowej wersji publicznej.

Metody, które będą używane najbardziej z delegatów, to `Invoke()` i `BeginInvoke()`  /  `EndInvoke()` . `Invoke()`wywoła wszystkie metody, które zostały dołączone do określonego wystąpienia delegata. Jak wspomniano powyżej, zazwyczaj wywołuje się delegatów przy użyciu składni wywołania metody w zmiennej delegat. Jak widać [w dalszej części tej serii](delegates-patterns.md), istnieją wzorce, które współpracują bezpośrednio z tymi metodami.

Teraz, gdy znasz składnię języka i klasy, które obsługują delegatów, sprawdźmy, jak są używane, tworzone i wywoływane delegatów o jednoznacznie określonym typie.

[Dalej](delegates-strongly-typed.md)
