---
title: Wyliczenia
description: 'Dowiedz się, jak używać wyliczenia F # zamiast literałów, aby kod był bardziej czytelny i konserwowany.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812110"
---
# <a name="enumerations"></a>Wyliczenia

*Wyliczenia*, znane także jako *wyliczenia*, są typami całkowitymi, w których etykiety są przypisywane do podzestawu wartości. Można ich użyć zamiast literałów, aby kod był bardziej czytelny i możliwy do utrzymania.

## <a name="syntax"></a>Składnia

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Uwagi

Wyliczenie wygląda podobnie jak Unia rozłączna, która ma proste wartości, z tą różnicą, że można określić wartości. Wartości są zwykle liczbami całkowitymi, które zaczynają się od 0 lub 1 lub liczby całkowite reprezentujące pozycje bitowe. Jeśli Wyliczenie jest przeznaczone do reprezentowania pozycji bitowych, należy również użyć atrybutu [flags](xref:System.FlagsAttribute) .

Typ podstawowy wyliczenia jest określany na podstawie literału, który jest używany, aby na przykład można było użyć literałów z sufiksem, takim jak `1u` , `2u` , i tak dalej, dla typu Liczba całkowita bez znaku ( `uint32` ).

Gdy odwołujesz się do nazwanych wartości, musisz użyć nazwy typu wyliczenia jako kwalifikatora, czyli `enum-name.value1` nie tylko `value1` . To zachowanie różni się od tych związków rozłącznych. Wynika to z faktu, że wyliczenia mają zawsze atrybut [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) .

Poniższy kod przedstawia deklarację i użycie wyliczenia.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Wyliczenia można łatwo przekonwertować na typ podstawowy przy użyciu odpowiedniego operatora, jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Typy wyliczeniowe mogą mieć jeden z następujących typów podstawowych: `sbyte` ,,,,, `byte` `int16` `uint16` `int32` `uint32` , `int64` , `uint16` , `uint64` , i `char` . Typy wyliczeniowe są reprezentowane w .NET Framework jako typy dziedziczone z `System.Enum` , które z kolei są dziedziczone z `System.ValueType` . Z tego względu są to typy wartości, które znajdują się na stosie lub są wbudowane w obiekt zawierający, a każda wartość typu podstawowego jest prawidłową wartością wyliczenia. Jest to istotne w przypadku dopasowania wzorców do wartości wyliczenia, ponieważ należy dostarczyć wzorzec, który przechwytuje wartości nienazwanych.

`enum`Funkcja w bibliotece języka F # może służyć do generowania wartości wyliczenia, nawet wartości innej niż jedna ze wstępnie zdefiniowanych wartości nazwanych. Używasz `enum` funkcji w następujący sposób.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Funkcja Domyślna `enum` działa z typem `int32` . W związku z tym nie można jej używać z typami wyliczeniowymi, które mają inne typy podstawowe. Zamiast tego należy użyć poniższego polecenia.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Ponadto przypadki wyliczeniowe są zawsze emitowane jako `public` . Jest to tak, aby były wyrównane do języka C# i reszty platformy .NET.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Rzutowanie i konwersje](casting-and-conversions.md)
