---
title: Wyrażenia z opóźnionym obliczaniem
description: 'Dowiedz się, jak wyrażenia opóźnione języka F # mogą zwiększyć wydajność aplikacji i bibliotek.'
ms.date: 08/15/2020
ms.openlocfilehash: 71c466ca3b74c9e92b81a3c268e07438ec944905
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558091"
---
# <a name="lazy-expressions"></a>Wyrażenia z opóźnionym obliczaniem

*Wyrażenia z opóźnieniem* to wyrażenia, które nie są obliczane natychmiast, ale zamiast tego są oceniane, gdy wynik jest wymagany. Może to pomóc poprawić wydajność kodu.

## <a name="syntax"></a>Składnia

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni *wyrażenie* ma kod, który jest oceniany tylko wtedy, gdy wynik jest wymagany, a *Identyfikator* jest wartością, która przechowuje wynik. Wartość jest typu [`Lazy<'T>`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazy-1-0.html) , gdzie rzeczywisty typ, który jest używany dla, `'T` jest określany na podstawie wyniku wyrażenia.

Wyrażenia z opóźnieniem umożliwiają poprawienie wydajności przez ograniczenie wykonywania wyrażeń tylko do tych sytuacji, w których jest wymagany wynik.

Aby wymusić wykonywanie wyrażeń, należy wywołać metodę `Force` . `Force` powoduje, że wykonywanie wykonuje się tylko jeden raz. Kolejne wywołania `Force` zwracają ten sam wynik, ale nie wykonują żadnego kodu.

Poniższy kod ilustruje użycie wyrażeń z opóźnieniem i użycie `Force` . W tym kodzie typ `result` jest `Lazy<int>` , a `Force` Metoda zwraca `int` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Ocena z opóźnieniem, ale nie `Lazy` Typ, jest również używana dla sekwencji. Aby uzyskać więcej informacji, zobacz [sekwencje](sequences.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Moduł LazyExtensions](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
