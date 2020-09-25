---
description: modyfikator parametru — odwołanie w C#
title: modyfikator parametru — odwołanie w C#
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: b9cd308a1eaf2ae8f4e3e89b1a4770933b3978cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188411"
---
# <a name="in-parameter-modifier-c-reference"></a>w modyfikatorze parametru (odwołanie w C#)

`in`Słowo kluczowe powoduje, że argumenty są przekazane przez odwołanie. Sprawia, że parametr formalny jest aliasem dla argumentu, który musi być zmienną. Innymi słowy, każda operacja na parametrze jest wykonywana na argumencie. Przypomina słowa kluczowe [ref](ref.md) lub [out](out-parameter-modifier.md) , z wyjątkiem tego, że `in` argumenty nie mogą być modyfikowane przez wywołaną metodę. `ref`Argumenty mogą być modyfikowane, `out` argumenty muszą być modyfikowane przez wywołana metoda i te modyfikacje są zauważalne w kontekście wywołującym.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

Powyższy przykład pokazuje, że `in` modyfikator zazwyczaj nie jest zbędny w miejscu wywołania. Jest to wymagane tylko w deklaracji metody.

> [!NOTE]
> `in`Słowo kluczowe może być również używane z parametrem typu ogólnego, aby określić, że parametr typu jest kontrawariantne, jako część `foreach` instrukcji lub jako część `join` klauzuli w zapytaniu LINQ. Aby uzyskać więcej informacji na temat używania `in` słowa kluczowego w tych kontekstach, zobacz sekcję [w](in.md), która zawiera linki do wszystkich tych celów.
  
Zmienne przekazane jako `in` argumenty muszą być zainicjowane przed przekazywaniem w wywołaniu metody. Jednak wywołana metoda nie może przypisywać wartości ani modyfikować argumentu.  

`in`Modyfikator parametru jest dostępny w języku C# 7,2 i nowszych. Poprzednie wersje generują błąd kompilatora `CS8107` ("funkcja ReadOnly References" nie jest dostępna w języku C# 7,0. Użyj języka w wersji 7,2 lub nowszej. ") Aby skonfigurować wersję języka kompilatora, zobacz [Wybieranie wersji języka C#](../configure-language-version.md).

`in` `ref` Słowa kluczowe, i `out` nie są uważane za część podpisu metody na potrzeby rozpoznawania przeciążenia. W związku z tym metody nie mogą być przeciążone, jeśli jedyną różnicą jest to, że jedna metoda przyjmuje `ref` argument lub, `in` a druga przyjmuje `out` argument. Poniższy kod, na przykład, nie zostanie skompilowany:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Przeciążanie na podstawie obecności `in` jest dozwolone:  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a>Reguły rozpoznawania przeciążenia

Można zrozumieć reguły rozpoznawania przeciążeń dla metod za pomocą wartości przez wartość a `in` argumenty, opisując motywację `in` argumentów. Definiowanie metod przy użyciu `in` parametrów jest potencjalną optymalizacją wydajności. Niektóre `struct` argumenty typu mogą być duże, a gdy metody są wywoływane przy użyciu ścisłych pętli lub ścieżek kodu krytycznego, koszt kopiowania tych struktur jest krytyczny. Metody deklarują `in` Parametry, aby określić, że argumenty mogą być przekazane przez odwołanie bezpiecznie, ponieważ wywołana metoda nie modyfikuje stanu tego argumentu. Przekazanie tych argumentów przez odwołanie pozwala uniknąć (potencjalnie) kosztownego kopiowania.

Określanie `in` dla argumentów w miejscu wywołania jest zwykle opcjonalne. Między przekazywaniem argumentów przez wartość i przekazaniem ich przez odwołanie za pomocą modyfikatora nie ma różnicy semantycznej `in` . `in`Modyfikator w miejscu wywołania jest opcjonalny, ponieważ nie trzeba wskazywać, że wartość argumentu może zostać zmieniona. Modyfikator można jawnie dodać `in` w miejscu wywołania, aby upewnić się, że argument jest przekazaniem przez odwołanie, a nie przez wartość. Jawne użycie `in` ma dwa następujące efekty:

Po pierwsze, określenie `in` w witrynie wywołania wymusza, aby kompilator wybierał metodę zdefiniowaną za pomocą zgodnego `in` parametru. W przeciwnym razie, gdy dwie metody różnią się tylko w obecności `in` , Przeciążenie przez wartość jest lepszym dopasowaniem.

Po drugie, określenie `in` deklaruje intencję przekazania argumentu przez odwołanie. Argument używany z `in` musi reprezentować lokalizację, do której można bezpośrednio odwoływać się. Te same reguły ogólne dla `out` i `ref` argumenty mają zastosowanie: nie można użyć stałych, zwykłych właściwości ani innych wyrażeń, które tworzą wartości. W przeciwnym razie pomijanie `in` w witrynie wywołania informuje kompilator, że umożliwi to utworzenie zmiennej tymczasowej do przekazania przez odwołanie tylko do odczytu do metody. Kompilator tworzy zmienną tymczasową, aby przezwyciężyć kilka ograniczeń z `in` argumentami:

- Zmienna tymczasowa dopuszcza stałe w czasie kompilacji jako `in` parametry.
- Zmienna tymczasowa pozwala na właściwości lub inne wyrażenia dla `in` parametrów.
- Zmienna tymczasowa zezwala na argumenty, w których istnieje niejawna konwersja z typu argumentu na typ parametru.

We wszystkich poprzednich wystąpieniach kompilator tworzy zmienną tymczasową, która przechowuje wartość stałej, właściwości lub innego wyrażenia.

Poniższy kod ilustruje następujące reguły:

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

Teraz Załóżmy, że jest dostępna inna metoda używająca argumentów wartości. Wyniki są zmieniane, jak pokazano w poniższym kodzie:

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

Jedyne wywołanie metody, do którego argument jest przenoszona przez odwołanie jest ostatnim z nich.

> [!NOTE]
> Poprzedni kod używa `int` jako typu argumentu dla uproszczenia. Ponieważ nie `int` jest większy niż odwołanie w większości nowoczesnych maszyn, nie ma zalet przekazywania jednego `int` jako odwołania tylko do odczytu.

## <a name="limitations-on-in-parameters"></a>Ograniczenia dotyczące `in` parametrów

Nie można używać `in` `ref` słów kluczowych, i `out` dla następujących rodzajów metod:  
  
- Metody asynchroniczne zdefiniowane za pomocą modyfikatora [Async](async.md) .  
- Metody iteratorów, które zawierają instrukcję [yield return](yield.md) lub `yield break` .
- Pierwszy argument metody rozszerzenia nie może mieć `in` modyfikatora, chyba że ten argument jest strukturą.
- Pierwszy argument metody rozszerzenia, gdzie ten argument jest typem ogólnym (nawet wtedy, gdy ten typ jest ograniczony do struktury).

## <a name="c-language-specification"></a>Specyfikacja języka C#  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Parametry metody](method-parameters.md)
- [Zapisz bezpieczny wydajny kod](../../write-safe-efficient-code.md)
