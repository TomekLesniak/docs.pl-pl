---
description: ref — słowo kluczowe — odwołanie w C#
title: ref — słowo kluczowe — odwołanie w C#
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 58a4ce30e11ca023b50e5e53b1f1554a30d44390
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137087"
---
# <a name="ref-c-reference"></a>ref (odwołanie w C#)

`ref`Słowo kluczowe wskazuje wartość, która jest przenoszona przez odwołanie. Jest on używany w czterech różnych kontekstach:

- W sygnaturze metody i w wywołaniu metody, aby przekazać argument do metody przez odwołanie. Aby uzyskać więcej informacji, zobacz [przekazywanie argumentu przez odwołanie](#passing-an-argument-by-reference).
- W podpisie metody, aby zwrócić wartość do obiektu wywołującego przez odwołanie. Aby uzyskać więcej informacji, zobacz [odwołania do zwracanych wartości](#reference-return-values).
- W treści elementu członkowskiego, aby wskazać, że wartość zwracana przez odwołanie jest przechowywana lokalnie jako odwołanie, które obiekt wywołujący zamierza zmodyfikować lub ogólnie rzecz biorąc, zmienna lokalna uzyskuje dostęp do innej wartości przez odwołanie. Aby uzyskać więcej informacji, zobacz [odwołania lokalne](#ref-locals).
- W `struct` deklaracji do deklarowania `ref struct` lub `readonly ref struct` . Aby uzyskać więcej informacji, zobacz sekcję [ `ref` struktury](../builtin-types/struct.md#ref-struct) w artykule [typy struktury](../builtin-types/struct.md) .

## <a name="passing-an-argument-by-reference"></a>Przekazywanie argumentu przez odwołanie

W przypadku użycia na liście parametrów metody `ref` słowo kluczowe wskazuje, że argument jest przenoszona przez odwołanie, a nie przez wartość. `ref`Słowo kluczowe powoduje, że parametr formalny jest aliasem dla argumentu, który musi być zmienną. Innymi słowy, każda operacja na parametrze jest wykonywana na argumencie. Na przykład, jeśli obiekt wywołujący przekazuje wyrażenie zmiennej lokalnej lub wyrażenie dostępu do elementu tablicy, a wywoływana metoda zastępuje obiekt, do którego odwołuje się parametr ref, wówczas zmienna lokalna obiektu wywołującego lub element array odwołuje się teraz do nowego obiektu, gdy metoda zwraca.

> [!NOTE]
> Nie należy mylić koncepcji przekazywania przez odwołanie z koncepcją typów referencyjnych. Te dwa koncepcje nie są takie same. Parametr metody można zmodyfikować, `ref` niezależnie od tego, czy jest to typ wartości, czy też typ referencyjny. Nie istnieje opakowanie typu wartości, gdy jest ono przesyłane przez odwołanie.  

Aby użyć `ref` parametru, zarówno definicja metody, jak i Metoda wywołująca muszą jawnie użyć `ref` słowa kluczowego, jak pokazano w poniższym przykładzie.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

Argument, który jest przesyłany do `ref` `in` parametru lub musi zostać zainicjowany przed jego przekazaniem. Różni się to od parametrów [out](out-parameter-modifier.md) , których argumenty nie muszą być jawnie inicjowane przed ich przekazaniem.

Elementy członkowskie klasy nie mogą mieć sygnatur, które różnią się tylko przez `ref` , `in` lub `out` . Błąd kompilatora występuje, jeśli jedyną różnicą między dwoma elementami członkowskimi tego typu jest, że jeden z nich ma `ref` parametr, a drugi ma `out` parametr, lub `in` . Poniższy kod, na przykład, nie kompiluje.  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

Jednakże metody mogą być przeciążone, gdy jedna metoda ma parametr `ref` , `in` , lub, `out` a drugi ma parametr value, jak pokazano w poniższym przykładzie.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 W innych sytuacjach, które wymagają dopasowania podpisu, takich jak ukrywanie lub zastępowanie, `in` , `ref` , i `out` są częścią podpisu i nie pasują do siebie nawzajem.  
  
 Właściwości nie są zmiennymi. Są to metody i nie można ich przekazywać do `ref` parametrów.  
  
 Nie można używać `ref` `in` słów kluczowych, i `out` dla następujących rodzajów metod:  
  
- Metody asynchroniczne zdefiniowane za pomocą modyfikatora [Async](async.md) .  
- Metody iteratorów, które zawierają instrukcję [yield return](yield.md) lub `yield break` .

Ponadto [metody rozszerzające](../../programming-guide/classes-and-structs/extension-methods.md) mają następujące ograniczenia:

- `out`Nie można użyć słowa kluczowego dla pierwszego argumentu metody rozszerzenia.
- `ref`Nie można użyć słowa kluczowego dla pierwszego argumentu metody rozszerzenia, jeśli argument nie jest strukturą lub typ ogólny nie jest ograniczony do struktury.
- `in`Nie można użyć słowa kluczowego, chyba że pierwszy argument jest strukturą. `in`Nie można użyć słowa kluczowego w żadnym typie ogólnym, nawet jeśli jest to struktura.

## <a name="passing-an-argument-by-reference-an-example"></a>Przekazywanie argumentu przez odwołanie: przykład

Poprzednie przykłady przechodzą typy wartości według odwołania. Możesz również użyć `ref` słowa kluczowego, aby przekazać typy odwołań przez odwołanie. Przekazywanie typu referencyjnego przez odwołanie włącza wywoływaną metodę, aby zastąpić obiekt, do którego odwołuje się parametr Reference w wywołującym. Lokalizacja przechowywania obiektu jest przenoszona do metody jako wartość parametru Reference. Jeśli zmienisz wartość w lokalizacji magazynu parametru (w celu wskazywania nowego obiektu), zmienisz również lokalizację magazynu, do którego odwołuje się obiekt wywołujący. Poniższy przykład przekazuje wystąpienie typu odwołania jako `ref` parametr.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Aby uzyskać więcej informacji na temat przekazywania typów odwołań według wartości i według odwołania, zobacz [przekazywanie parametrów typu odwołania](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Odwoływanie się do zwracanych wartości

Wartości zwracane przez odwołanie (lub zwroty odwołań) to wartości, które Metoda zwraca przez odwołanie do obiektu wywołującego. Oznacza to, że obiekt wywołujący może zmodyfikować wartość zwróconą przez metodę, a ta zmiana jest odzwierciedlona w stanie obiektu w metodzie wywołującej.

Wartość zwracana przez odwołanie jest definiowana za pomocą `ref` słowa kluczowego:

- W podpisie metody. Na przykład następująca sygnatura metody wskazuje, że `GetCurrentPrice` Metoda zwraca <xref:System.Decimal> wartość przez odwołanie.

```csharp
public ref decimal GetCurrentPrice()
```

- Między `return` tokenem i zmienną zwróconą w `return` instrukcji w metodzie. Przykład:

```csharp
return ref DecimalArray[0];
```

Aby obiekt wywołujący zmodyfikował stan obiektu, wartość zwracana odwołania musi być przechowywana w zmiennej, która jest jawnie zdefiniowana jako [lokalna jako ref](#ref-locals).

Poniżej znajduje się bardziej kompletny przykład powrotu odwołania, pokazujący zarówno podpis metody, jak i treść metody.

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

Wywołana metoda może również deklarować wartość zwracaną jako `ref readonly` zwracającą wartość przez odwołanie i wymusić, że wywoływany kod nie może zmodyfikować zwracanej wartości. Metoda wywołująca może uniknąć kopiowania zwracanej wartości przez zapisanie wartości w lokalnej zmiennej [ref ReadOnly](#ref-readonly-locals) .

Aby zapoznać się z przykładem, zobacz [przykład ref Returns i ref locales](#a-ref-returns-and-ref-locals-example).

## <a name="ref-locals"></a>Odwołania lokalne

Referencyjna zmienna lokalna służy do odwoływania się do wartości zwracanych przy użyciu `return ref` . Nie można zainicjować zmiennej lokalnej ref do wartości zwracanej niebędącej odwołaniem. Innymi słowy, prawa strona inicjowania musi być odwołaniem. Wszelkie modyfikacje wartości lokalnego elementu ref są odzwierciedlane w stanie obiektu, którego Metoda zwróciła wartość przez odwołanie.

Można zdefiniować odwołanie lokalne przy użyciu `ref` słowa kluczowego przed deklaracją zmiennej, a także bezpośrednio przed wywołaniem metody, która zwraca wartość przez odwołanie.

Na przykład poniższa instrukcja definiuje wartość lokalną ref zwracaną przez metodę o nazwie `GetEstimatedValue` :

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

Możesz uzyskać dostęp do wartości przez odwołanie w ten sam sposób. W niektórych przypadkach uzyskanie dostępu do wartości przez odwołanie zwiększa wydajność poprzez uniknięcie potencjalnie kosztownej operacji kopiowania. Na przykład poniższa instrukcja pokazuje, jak jedna z nich może definiować wartość lokalna ref, która jest używana do odwoływania się do wartości.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

W obu przykładach `ref` słowo kluczowe musi być używane w obu miejscach lub kompilator generuje błąd CS8172, "nie można zainicjować zmiennej przez odwołanie za pomocą wartości".

Począwszy od języka C# 7,3, Zmienna iteracji `foreach` instrukcji może być lokalna lokalną lub ref tylko do odczytu zmienna lokalna. Aby uzyskać więcej informacji, zobacz artykuł [instrukcji foreach](foreach-in.md) .

Zaczynając od języka C# 7,3, można ponownie przypisać lokalną zmienną lokalną lub ref ReadOnly do odczytu za pomocą [operatora przypisania ref](../operators/assignment-operator.md#ref-assignment-operator).

## <a name="ref-readonly-locals"></a>Odwołania do elementów lokalnych ReadOnly

Wartość Ref Local ReadOnly jest używana do odwoływania się do wartości zwracanych przez metodę lub właściwość, która ma `ref readonly` w jej podpisie i używa `return ref` . `ref readonly`Zmienna łączy właściwości `ref` zmiennej lokalnej ze `readonly` zmienną: jest to alias do magazynu, do którego jest przypisany, i nie może być modyfikowany.

## <a name="a-ref-returns-and-ref-locals-example"></a>Przykład odwołania ref i lokalne odwołania ref

W poniższym przykładzie zdefiniowano `Book` klasę, która ma dwa <xref:System.String> pola `Title` i `Author` . Definiuje również `BookCollection` klasę, która zawiera prywatną tablicę `Book` obiektów. Poszczególne obiekty książek są zwracane przez odwołanie poprzez wywołanie `GetBookByTitle` metody.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Gdy obiekt wywołujący przechowuje wartość zwróconą przez `GetBookByTitle` metodę jako odwołanie lokalne, zmiany, które obiekt wywołujący wprowadza do wartości zwracanej, są odzwierciedlone w `BookCollection` obiekcie, jak pokazano w poniższym przykładzie.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też

- [Zapisz bezpieczny wydajny kod](../../write-safe-efficient-code.md)
- [Wartości zwracane ref i zmienne lokalne ref](../../programming-guide/classes-and-structs/ref-returns.md)
- [Wyrażenie warunkowe ref](../operators/conditional-operator.md#conditional-ref-expression)
- [Przekazywanie parametrów](../../programming-guide/classes-and-structs/passing-parameters.md)
- [Parametry metody](method-parameters.md)
- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
