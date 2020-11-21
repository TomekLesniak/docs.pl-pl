---
title: Typy referencyjne dopuszczające wartość null
description: Ten artykuł zawiera omówienie typów referencyjnych dopuszczających wartość null, które dodano w języku C# 8,0. Dowiesz się, jak funkcja zapewnia bezpieczeństwo przed wyjątkami odwołania o wartości null dla nowych i istniejących projektów.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: b4906987ee23f458c1da9754ed7b402621169f63
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099347"
---
# <a name="nullable-reference-types"></a>Typy referencyjne dopuszczające wartość null

W języku C# 8,0 wprowadzono **wartości null typów referencyjnych** i **niedopuszczających wartości null** , które umożliwiają wykonywanie ważnych instrukcji dotyczących właściwości dla zmiennych typu odwołania:

- **Odwołanie nie powinno mieć wartości null**. Gdy zmienne nie powinny mieć wartości null, kompilator wymusza reguły, które zapewnią bezpieczne odtworzenie odwołania do tych zmiennych bez uprzedniego sprawdzenia, czy nie ma on wartości null:
  - Zmienna musi być zainicjowana do wartości innej niż null.
  - Do zmiennej nigdy nie można przypisać wartości `null` .
- **Odwołanie może mieć wartość null**. Gdy zmienne mogą mieć wartość null, kompilator wymusza różne reguły, aby upewnić się, że prawidłowo sprawdzono odwołanie o wartości null:
  - Zmienna może zostać wykorzystana tylko wtedy, gdy kompilator może zagwarantować, że wartość nie ma wartości null.
  - Te zmienne mogą być inicjowane z `null` wartością domyślną i mogą mieć przypisaną wartość `null` w innym kodzie.

Ta nowa funkcja zapewnia znaczne korzyści w porównaniu z obsługą zmiennych referencyjnych we wcześniejszych wersjach języka C#, w których nie można ustalić zamiaru projektowania na podstawie deklaracji zmiennej. Kompilator nie zapewniał bezpieczeństwa przed wyjątkami odwołania o wartości null dla typów referencyjnych:

- **Odwołanie może mieć wartość null**. Kompilator nie wydaje ostrzeżeń, gdy zmienna typu odwołania jest zainicjowana do `null` lub później przypisany `null` . Kompilator wystawia ostrzeżenia, gdy te zmienne są wywołujące bez sprawdzania wartości null.
- **Przyjęto, że odwołanie nie ma wartości null**. Kompilator nie wystawia żadnych ostrzeżeń, gdy odwołania do typów odwołań. Kompilator wystawia ostrzeżenia, jeśli zmienna jest ustawiona na wyrażenie, które może mieć wartość null.

Te ostrzeżenia są emitowane w czasie kompilacji. Kompilator nie dodaje żadnych kontroli wartości null ani innych konstrukcji środowiska uruchomieniowego w kontekście dopuszczającym wartość null. W czasie wykonywania, odwołanie do wartości null i odwołanie niedopuszczające wartości null są równoważne.

Przy dodawaniu typów odwołań do wartości null można zadeklarować cel dokładniej. `null`Wartość jest poprawnym sposobem reprezentowania, że zmienna nie odwołuje się do wartości. Nie używaj tej funkcji, aby usunąć wszystkie `null` wartości z Twojego kodu. Zamiast tego należy zadeklarować intencję do kompilatora i innych deweloperów, które odczytują swój kod. Deklarując swój intencję, kompilator informuje, gdy piszesz kod, który jest niespójny z tym zamiarem.

**Typ referencyjny dopuszczający wartość null** jest zanotowany przy użyciu tej samej składni co [typy wartości null](language-reference/builtin-types/nullable-value-types.md): a `?` jest dołączany do typu zmiennej. Na przykład następująca deklaracja zmiennej reprezentuje zmienną ciągu null, `name` :

```csharp
string? name;
```

Każda zmienna, w której `?` nie jest dołączana do nazwy typu, jest **typem referencyjnym, który nie dopuszcza wartości null**. Zawiera wszystkie zmienne typu referencyjnego w istniejącym kodzie po włączeniu tej funkcji.

Kompilator używa statycznej analizy do ustalenia, czy odwołanie dopuszczające wartość null jest znane jako inne niż null. Kompilator ostrzega o tym, jeśli odwołujesz się do odwołania do wartości null, jeśli może to mieć wartość null. Zachowanie to można zastąpić za pomocą [operatora null-łagodniejszej](language-reference/operators/null-forgiving.md) `!` po nazwie zmiennej. Jeśli na przykład wiadomo, że `name` zmienna nie ma wartości null, ale kompilator generuje ostrzeżenie, można napisać następujący kod, aby zastąpić analizę kompilatora:

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a>Wartość zerowa typów

Każdy typ referencyjny może mieć jeden z czterech *nullabilities*, który opisuje, kiedy generowane są ostrzeżenia:

- *Niedopuszczający wartości null*: nie można przypisać wartości null do zmiennych tego typu. Przed usunięciem odwołania zmienne tego typu nie muszą mieć wartości null.
- *Nullable*: wartość null może być przypisana do zmiennych tego typu. Odwołujące się do zmiennych tego typu bez uprzedniego sprawdzenia `null` powoduje ostrzeżenie.
- *Oblivious*: Oblivious jest stanem sprzed C # 8,0. Zmienne tego typu mogą być wywoływane lub przypisane bez ostrzeżeń.
- *Nieznany*: nieznany jest zazwyczaj dla parametrów typu, w których ograniczenia nie informują kompilatora, że typ musi *dopuszczać wartości null* lub nie *dopuszczać wartości null*.

Wartość null typu w deklaracji zmiennej jest kontrolowana przez *kontekst dopuszczający wartość* null, w którym zmienna jest zadeklarowana.

## <a name="nullable-contexts"></a>Konteksty dopuszczające wartość null

Konteksty dopuszczające wartość null umożliwiają precyzyjne kontrolowanie, w jaki sposób kompilator interpretuje zmienne typu odwołania. **Kontekst adnotacji dopuszczający wartość null** w dowolnym wierszu źródłowym jest włączony lub wyłączony. Można traktować kompilator pre-C # 8,0 jako Kompilowanie całego kodu w wyłączonym kontekście dopuszczania wartości null: dowolny typ referencyjny może mieć wartość null. **Kontekst ostrzeżeń dopuszczających wartość null** może być również włączony lub wyłączony. Kontekst ostrzeżeń dopuszczających wartość null określa ostrzeżenia generowane przez kompilator przy użyciu analizy przepływu.

Kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia dopuszczający wartość null można ustawić dla projektu przy użyciu `Nullable` elementu w pliku *. csproj* . Ten element określa, w jaki sposób kompilator interpretuje wartość null typów i jakie ostrzeżenia są generowane. Prawidłowe ustawienia to:

- `enable`: Kontekst adnotacji z dopuszczaniem wartości null jest **włączony**. Kontekst ostrzegawczy dopuszczający wartość null jest **włączony**.
  - Zmienne typu referencyjnego, `string` na przykład, nie dopuszczają wartości null.  Wszystkie ostrzeżenia o wartości null są włączone.
- `warnings`: Kontekst adnotacji dopuszczający wartość null jest **wyłączony**. Kontekst ostrzegawczy dopuszczający wartość null jest **włączony**.
  - Zmienne typu referencyjnego to Oblivious. Wszystkie ostrzeżenia o wartości null są włączone.
- `annotations`: Kontekst adnotacji z dopuszczaniem wartości null jest **włączony**. Kontekst ostrzegawczy dopuszczający wartość null jest **wyłączony**.
  - Zmienne typu referencyjnego, ciąg na przykład, nie dopuszczają wartości null. Wszystkie ostrzeżenia o wartości null są wyłączone.
- `disable`: Kontekst adnotacji dopuszczający wartość null jest **wyłączony**. Kontekst ostrzegawczy dopuszczający wartość null jest **wyłączony**.
  - Zmienne typu referencyjnego to Oblivious, podobnie jak w przypadku wcześniejszych wersji języka C#. Wszystkie ostrzeżenia o wartości null są wyłączone.

**Przykład**:

```xml
<Nullable>enable</Nullable>
```

Możesz również użyć dyrektyw, aby ustawić te same konteksty w dowolnym miejscu w projekcie:

- `#nullable enable`: Ustawia kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia nullable do **włączenia**.
- `#nullable disable`: Ustawia kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia dopuszczający wartość **null.**
- `#nullable restore`: Przywraca kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia do wartości null w ustawieniach projektu.
- `#nullable disable warnings`: Ustaw dla kontekstu ostrzeżenia o wartości null wartość **wyłączone**.
- `#nullable enable warnings`: Ustaw kontekst ostrzegawczy dopuszczający wartość **null.**
- `#nullable restore warnings`: Przywraca kontekst ostrzegawczy dopuszczający wartość null do ustawień projektu.
- `#nullable disable annotations`: Ustaw dla kontekstu adnotacji wartości null wartość **wyłączone**.
- `#nullable enable annotations`: Ustaw dla kontekstu adnotacji nullable wartość **włączone**.
- `#nullable restore annotations`: Przywraca kontekst ostrzeżenia adnotacji do ustawień projektu.

> [!IMPORTANT]
> Globalny kontekst dopuszczający wartość null nie ma zastosowania do wygenerowanych plików kodu. W ramach którejkolwiek z tych strategii kontekst dopuszczający wartość null jest *wyłączony* dla każdego pliku źródłowego oznaczonego jako wygenerowany. Oznacza to, że wszystkie interfejsy API w wygenerowanych plikach nie są adnotacjami. Istnieją cztery sposoby, aby plik został oznaczony jako wygenerowany:
>
> 1. W pliku. editorconfig Określ `generated_code = true` w sekcji, która odnosi się do tego plik.
> 1. Umieść `<auto-generated>` lub `<auto-generated/>` w komentarzu w górnej części pliku. Może znajdować się w dowolnym wierszu tego komentarza, ale blok komentarza musi być pierwszym elementem w pliku.
> 1. Uruchom nazwę pliku z *TemporaryGeneratedFile_*
> 1. Zakończ nazwę pliku z rozszerzeniem *. Designer.cs*, *. generated.cs*, *. g.cs* lub *. g.i.cs*.
>
> Generatory mogą wyrazić zgodę na użycie [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) dyrektywy preprocesora.

Domyślnie adnotacja null i konteksty ostrzeżeń są **wyłączone**, w tym nowych projektów. Oznacza to, że istniejący kod kompiluje się bez zmian i nie generuje żadnych nowych ostrzeżeń.

Te opcje zapewniają dwie odrębne strategie [aktualizowania istniejącej bazy kodu](nullable-migration-strategies.md) w celu użycia typów referencyjnych dopuszczających wartość null.

## <a name="nullable-annotation-context"></a>Kontekst adnotacji dopuszczający wartość null

Kompilator używa następujących reguł w wyłączonym kontekście adnotacji nullable:

- Nie można zadeklarować odwołań do wartości null w wyłączonym kontekście.
- Wszystkie zmienne odwołania mogą mieć przypisaną wartość null.
- Nie są generowane żadne ostrzeżenia, gdy zmienna typu odwołania jest wykorzystana.
- Operatora null-łagodniejszej nie można używać w wyłączonym kontekście.

Zachowanie jest takie samo jak w poprzednich wersjach języka C#.

Kompilator używa następujących reguł w włączonym kontekście adnotacji dopuszczających wartość null:

- Dowolna zmienna typu referencyjnego jest **odwołaniem niedopuszczanym do wartości null**.
- Wszystkie odwołania niedopuszczające wartości null mogą być bezpiecznie wywoływać.
- Dowolny typ referencyjny dopuszczający wartość null (zanotowany przez `?` po typie w deklaracji zmiennej) może mieć wartość null. Analiza statyczna określa, czy wartość jest znana jako inna niż null, gdy jest ona wywoływać. W przeciwnym razie kompilator wyświetli ostrzeżenie.
- Można użyć operatora null-łagodniejszej, aby zadeklarować, że odwołanie dopuszczające wartość null nie ma wartości null.

W włączonym kontekście dopuszczającym wartość null, `?` znak dołączony do typu referencyjnego deklaruje **typ referencyjny dopuszczający wartość null**. **Operator null-łagodniejszej** `!` może być dołączany do wyrażenia, aby zadeklarować, że wyrażenie nie ma wartości null.

## <a name="nullable-warning-context"></a>Kontekst ostrzegawczy dopuszczający wartość null

Kontekst ostrzeżenia dopuszczający wartość null jest różny od kontekstu adnotacji dopuszczającej wartość null. Ostrzeżenia można włączyć nawet wtedy, gdy nowe adnotacje są wyłączone. Kompilator używa statycznej analizy przepływu do określenia **stanu null** dowolnych odwołań. Stan o wartości null **nie ma wartości null** lub **może mieć wartość null** , jeśli *kontekst ostrzeżenia o wartości null* nie jest **wyłączony**. Jeśli odwołujesz się do odwołania, gdy kompilator ustalił, że **może mieć wartość null**, kompilator wyświetli ostrzeżenie. Stan odwołania może **mieć wartość null** , chyba że kompilator może określić jeden z dwóch warunków:

1. Zmienna ma w nieskończoność przypisaną wartość różną od null.
1. Zmienna lub wyrażenie zostało sprawdzone pod kątem wartości null przed usunięciem odwołania do niego.

Kompilator generuje ostrzeżenia, gdy zostanie wykorzystana zmienna lub wyrażenie, które **może mieć wartość null** w kontekście ostrzeżenia o wartości null. Co więcej, kompilator generuje ostrzeżenia, gdy zmienna typu odwołania, która nie ma wartości null, **może mieć zmienną null** lub wyrażenie w włączonym kontekście adnotacji nullable.

## <a name="attributes-describe-apis"></a>Opisy interfejsów API

Dodaj atrybuty do interfejsów API, które udostępniają kompilatorowi więcej informacji na temat sytuacji, gdy argumenty lub wartości zwracane mogą lub nie mogą mieć wartości null. Więcej informacji o tych atrybutach można znaleźć w naszym artykule w dokumentacji języka obejmującej [atrybuty dopuszczające wartość null](language-reference/attributes/nullable-analysis.md). Te atrybuty są dodawane do bibliotek .NET za pośrednictwem bieżących i przyszłych wersji. Najczęściej używane interfejsy API są aktualizowane jako pierwsze.

## <a name="known-pitfalls"></a>Znane pułapek

Tablice i struktury, które zawierają typy odwołań, są znane pułapek w funkcji typów referencyjnych dopuszczających wartość null.

### <a name="structs"></a>Struktury

Struktura, która zawiera typy odwołań niedopuszczających wartości null, umożliwia przypisanie `default` do niego bez żadnych ostrzeżeń. Rozpatrzmy następujący przykład:

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

W powyższym przykładzie nie ma żadnego ostrzeżenia w `PrintStudent(default)` czasie, gdy typy odwołań niedopuszczających wartości null `FirstName` i `LastName` mają wartość null.

Innym często spotykanym przypadkiem jest to, że należy zająć się ogólnymi strukturami. Rozpatrzmy następujący przykład:

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

W poprzednim przykładzie właściwość `Bar` ma być `null` w czasie wykonywania i jest przypisywana do niedopuszczających wartości null ciągów bez żadnych ostrzeżeń.

### <a name="arrays"></a>Tablice

Tablice są również znanymi Pitfall w typach referencyjnych dopuszczających wartość null. Rozważmy następujący przykład, który nie wygenerował żadnych ostrzeżeń:

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

W poprzednim przykładzie deklaracja tablicy pokazuje, że zawiera ciągi niedopuszczające wartości null, podczas gdy jego elementy są zainicjowane do wartości null. Następnie zmienna `s` ma przypisaną wartość null (pierwszy element tablicy). Na koniec zmienna jest usuwana z `s` powodu wyjątku czasu wykonywania.

## <a name="see-also"></a>Zobacz także

- [Specyfikacja typu referencyjnego dopuszczająca wartość null](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [Samouczek wprowadzający do odwołań do wartości null](tutorials/nullable-reference-types.md)
- [Migrowanie istniejącej bazy kodu do odwołań do wartości null](tutorials/upgrade-to-nullable-references.md)
- [-Nullable (opcja kompilatora C#)](language-reference/compiler-options/nullable-compiler-option.md)
