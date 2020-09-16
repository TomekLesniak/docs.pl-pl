---
title: Typy wyjątków
description: 'Dowiedz się, jak definiować i używać typów wyjątków języka F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557232"
---
# <a name="exception-types"></a>Typy wyjątków

Istnieją dwie kategorie wyjątków w języku F #: typy wyjątków platformy .NET i typy wyjątków języka F #. W tym temacie opisano sposób definiowania typów wyjątków języka F # i używania ich.

## <a name="syntax"></a>Składnia

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni *Typ wyjątku* to nazwa nowego typu wyjątku F #, a *argument-type* reprezentuje typ argumentu, który może być dostarczony podczas zgłaszania wyjątku tego typu. Można określić wiele argumentów za pomocą typu krotki dla *typu argumentu*.

Typowa definicja wyjątku języka F # jest podobna do poniższego.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Wyjątek tego typu można wygenerować przy użyciu `raise` funkcji w następujący sposób.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Możesz użyć typu wyjątku F # bezpośrednio w filtrach w `try...with` wyrażeniu, jak pokazano w poniższym przykładzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Typ wyjątku zdefiniowany za pomocą `exception` słowa kluczowego w F # to nowy typ, który dziedziczy po `System.Exception` .

## <a name="see-also"></a>Zobacz także

- [Obsługa wyjątków](index.md)
- [Wyjątki: `raise` Funkcja](the-raise-function.md)
- [Hierarchia wyjątków](../../../standard/exceptions/index.md)
