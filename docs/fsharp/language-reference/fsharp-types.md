---
title: Typy
description: 'Dowiedz się więcej na temat typów, które są używane w języku F # i jak typy języka F # mają nazwy i zostały opisane.'
ms.date: 08/15/2020
ms.openlocfilehash: a86d8e8f672d8399b02bb193ae04e1f0d46720b6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812071"
---
# <a name="f-types"></a>Typy F#

W tym temacie opisano typy, które są używane w języku F # oraz sposób nazywania i opisywania typów języka F #.

## <a name="summary-of-f-types"></a>Podsumowanie typów języka F #

Niektóre typy są uznawane za *typy pierwotne*, takie jak typ Boolean `bool` i typy całkowite i zmiennoprzecinkowe różnych rozmiarów, które obejmują typy dla bajtów i znaków. Te typy są opisane w [typach pierwotnych](basic-types.md).

Inne typy, które są wbudowane w język obejmują krotki, listy, tablice, sekwencje, rekordy i związki rozłącznych. Jeśli masz doświadczenie z innymi językami .NET i poznajesz język F #, należy zapoznać się z tematami dotyczącymi każdego z tych typów. Te typy specyficzne dla języka F # obsługują style programowania, które są wspólne dla funkcjonalnych języków programowania. Wiele z tych typów ma skojarzone moduły w bibliotece języka F #, które obsługują Typowe operacje na tych typach.

Typ funkcji zawiera informacje o typach parametrów i zwracanym typie.

.NET Framework jest źródłem typów obiektów, typów interfejsów, typów delegatów i innych. Możesz definiować własne typy obiektów tak samo jak w przypadku dowolnego innego języka .NET.

Ponadto kod języka F # może definiować aliasy, które są nazwanymi *skrótami*typów, które są alternatywnymi nazwami typów. Możesz użyć skrótów typu, gdy typ może ulec zmianie w przyszłości i chcesz uniknąć zmiany kodu, który zależy od typu. Lub można użyć skrótu typu jako przyjaznej nazwy dla typu, który może ułatwić odczytywanie i zrozumienie kodu.

Język F # zapewnia przydatne typy kolekcji, które są przeznaczone do programowania funkcjonalnego. Korzystanie z tych typów kolekcji ułatwia pisanie kodu, który jest bardziej funkcjonalny w stylu. Aby uzyskać więcej informacji, zobacz [typy kolekcji języka F #](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Składnia typów

W kodzie języka F # często trzeba napisać nazwy typów. Każdy typ ma formę składni, a te formy są używane w adnotacjach typu, deklaracjach metod abstrakcyjnych, deklaracjach delegatów, sygnaturach i innych konstrukcjach. Za każdym razem, gdy deklarujesz nową konstrukcję programu w interpreterze, interpreter wyświetla nazwę konstrukcji i składnię dla jej typu. Ta składnia może być tylko identyfikatorem typu zdefiniowanego przez użytkownika lub wbudowanym identyfikatorem, takim jak dla `int` lub `string` , ale dla bardziej złożonych typów, składnia jest bardziej skomplikowana.

W poniższej tabeli przedstawiono aspekty składni typów dla typów języka F #.

|Typ|Składnia typu|Przykłady|
|----|-----------|--------|
|typ pierwotny|*Nazwa typu*|`int`<br /><br />`float`<br /><br />`string`|
|typ agregacji (Klasa, struktura, Unia, rekord, Wyliczenie itd.)|*Nazwa typu*|`System.DateTime`<br /><br />`Color`|
|Skrót typu|*Type-skrót-Name*|`bigint`|
|w pełni kwalifikowany typ|*przestrzenie nazw. type-name*<br /><br />lub<br /><br />*modules. type-name*<br /><br />lub<br /><br />*przestrzenie nazw. modules. type-name*|`System.IO.StreamWriter`|
|array|*Nazwa typu*[] lub<br /><br />Tablica *nazw typu*|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|Tablica dwuwymiarowa|*Nazwa typu*[,]|`int[,]`<br /><br />`float[,]`|
|Tablica trójwymiarowa|*type-name*[,,]|`float[,,]`|
|tuple|*Typ-name1* &#42; *Type-NAME2* ...|Na przykład `(1,'b',3)` ma typ `int * char * int`|
|typ ogólny|*Typ-parametru* *rodzajowego-nazwa*<br /><br />lub<br /><br />*Nazwa* &lt; typu ogólnego *Lista parametrów typu*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|Typ skonstruowany (typ ogólny, który ma podany określony argument typu)|*Typ* — *typ ogólny-nazwa*<br /><br />lub<br /><br />*Nazwa* &lt; typu ogólnego *Lista argumentów typu*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|Typ funkcji, która ma jeden parametr|*parametr-Type1*  - &gt; *Typ zwracany*|Funkcja, która przyjmuje `int` i zwraca `string` Typ `int -> string`|
|Typ funkcji, która ma wiele parametrów|*parametr-Type1*  - &gt; *parametr-Type2*  - &gt; ...- &gt; *Typ zwracany*|Funkcja, która przyjmuje `int` i a `float` i zwraca `string` Typ `int -> float -> string`|
|wyższa funkcja Order jako parametr|(*Typ funkcji*)|`List.map` ma typ `('a -> 'b) -> 'a list -> 'b list`|
|delegate|delegat *typu funkcji*|`delegate of unit -> int`|
|Typ elastyczny|#*Nazwa typu*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Tematy pokrewne

|Temat|Opis|
|-----|-----------|
|[Typy pierwotne](basic-types.md)|Opisuje wbudowane typy proste, takie jak typy całkowite, typ Boolean i typy znaków.|
|[Typ jednostki](unit-type.md)|Opisuje `unit` Typ, typ, który ma jedną wartość i który jest wskazywany przez (); odpowiednikiem `void` w języku C# i `Nothing` w Visual Basic.|
|[Krotki](tuples.md)|Opisuje typ krotki, typ, który składa się z skojarzonych wartości dowolnego typu zgrupowanych w parach, potrójnie, czterokrotnie itd.|
|[Opcje](options.md)|Opisuje typ opcji, typ, który może mieć wartość lub być pusty.|
|[Listy](lists.md)|Opisuje listy, które są uporządkowane, z niemodyfikowalnymi seriami wszystkich elementów tego samego typu.|
|[Tablice](arrays.md)|Opisuje tablice, które są uporządkowanymi zestawami modyfikowalnych elementów tego samego typu, które zajmują ciągły blok pamięci i o stałym rozmiarze.|
|[Sekwencje](sequences.md)|Opisuje typ sekwencji, który reprezentuje serię logiczną wartości; poszczególne wartości są obliczane tylko w razie potrzeby.|
|[Rekordy](records.md)|Opisuje typ rekordu, niewielką wartość zagregowaną nazwanych wartości.|
|[Sumy rozłączne](discriminated-unions.md)|Opisuje typ Unii rozłącznych, którego wartości mogą być jednym z zestawów możliwych typów.|
|[Funkcje](./functions/index.md)|Opisuje wartości funkcji.|
|[Klasy](classes.md)|Opisuje typ klasy, typ obiektu, który odnosi się do typu referencyjnego platformy .NET. Typy klas mogą zawierać elementy członkowskie, właściwości, zaimplementowane interfejsy i typ podstawowy.|
|[Struktury](structures.md)|Opisuje `struct` Typ, typ obiektu, który odpowiada typowi wartości .NET. `struct`Typ zwykle reprezentuje niewielką wartość zagregowaną danych.|
|[Interfejsy](interfaces.md)|Opisuje typy interfejsów, które reprezentują zestaw elementów członkowskich, które udostępniają pewne funkcje, ale nie zawierają danych. Typ interfejsu musi być zaimplementowany przez typ obiektu, który ma być przydatny.|
|[Delegaci](delegates.md)|Opisuje typ delegata, który reprezentuje funkcję jako obiekt.|
|[Wyliczenia](enumerations.md)|Opisuje typy wyliczeniowe, których wartości należą do zestawu nazwanych wartości.|
|[Atrybuty](attributes.md)|Opisuje atrybuty, które są używane do określania metadanych dla innego typu.|
|[Typy wyjątków](./exception-handling/exception-types.md)|Opisuje wyjątki, które określają informacje o błędzie.|
