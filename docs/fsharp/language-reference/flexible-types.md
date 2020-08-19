---
title: Typy elastyczne
description: 'Dowiedz się, jak używać typu elastycznej adnotacji F #, która wskazuje, że parametr, zmienna lub wartość ma typ zgodny z określonym typem.'
ms.date: 08/15/2020
ms.openlocfilehash: 44241ad082cd7f3de9e0cc6a48b8a8946e7b33d3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557753"
---
# <a name="flexible-types"></a>Typy elastyczne

Typ *elastycznyj adnotacji* wskazuje, że parametr, zmienna lub wartość ma typ, który jest zgodny z określonym typem, gdzie zgodność jest określana na podstawie położenia w hierarchii obiektów klasy lub interfejsów zorientowanych na obiekt. Typy elastyczne są przydatne w przypadku, gdy konwersja automatyczna na typy wyższe w hierarchii typów nie występuje, ale mimo to chcesz włączyć funkcję do pracy z dowolnym typem w hierarchii lub dowolnym typem, który implementuje interfejs.

## <a name="syntax"></a>Składnia

```fsharp
#type
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni *Typ* reprezentuje typ podstawowy lub interfejs.

Elastyczny typ jest równoważny z typem ogólnym, który ma ograniczenie, które ogranicza dozwolone typy do typów, które są zgodne z typem podstawowym lub interfejsem. Oznacza to, że dwa następujące wiersze kodu są równoważne.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Elastyczne typy są przydatne w kilku typach sytuacji. Na przykład jeśli masz funkcję wyższej kolejności (funkcja, która przyjmuje funkcję jako argument), często przydatna jest funkcja zwracająca typ elastyczny. W poniższym przykładzie użycie elastycznego typu z argumentem sekwencji w `iterate2` Włącza funkcję wyższego rzędu do pracy z funkcjami, które generują sekwencje, tablice, listy i wszelkie inne wyliczalne typy.

Weź pod uwagę następujące dwie funkcje, z których jedna zwraca sekwencję, a druga zwraca typ elastyczny.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

W innym przykładzie należy rozważyć funkcję biblioteki [SEQ. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) :

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Do tej funkcji można przekazać dowolną z następujących wyliczalnych sekwencji:

- Lista list
- Lista tablic
- Tablica list
- Tablica sekwencji
- Wszystkie inne kombinacje wyliczalnych sekwencji

Poniższy kod służy `Seq.concat` do zademonstrowania scenariuszy, które można obsługiwać przy użyciu elastycznych typów.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

Dane wyjściowe są następujące:

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

W języku F #, podobnie jak w innych językach zorientowanych obiektowo, istnieją konteksty, w których typy pochodne lub typy implementujące interfejsy są automatycznie konwertowane na typ podstawowy lub typ interfejsu. Te konwersje automatyczne występują w argumentach bezpośrednich, ale nie w przypadku, gdy typ znajduje się w pozycji podrzędnej, jako część bardziej złożonego typu, takiego jak typ zwracany typu funkcji lub jako argument typu. W ten sposób, elastyczny zapis typu jest szczególnie przydatny, gdy typ, który jest stosowany, jest częścią bardziej złożonego typu.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Typy ogólne](./generics/index.md)
