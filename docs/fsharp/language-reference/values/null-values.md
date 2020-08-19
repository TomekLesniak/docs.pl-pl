---
title: Wartości zerowe
description: 'Dowiedz się, w jaki sposób wartość null jest używana w języku programowania F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 3b2c7ebe7b8eff08f7c3e76b9715ccab1bbd5d36
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558351"
---
# <a name="null-values"></a>Wartości zerowe

W tym temacie opisano, w jaki sposób wartość null jest używana w języku F #.

## <a name="null-value"></a>Wartość zerowa

Wartość null nie jest zwykle używana w języku F # dla wartości lub zmiennych. Jednak wartość null pojawia się jako nietypowa wartość w pewnych sytuacjach. Jeśli typ jest zdefiniowany w F #, null nie jest dozwolony jako wartość zwykła, chyba że atrybut [AllowNullLiteral](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-allownullliteralattribute.html#Value) jest stosowany do typu. Jeśli typ jest zdefiniowany w innym języku .NET, wartość null jest możliwa i w przypadku współdziałania z takimi typami kod języka F # może napotkać wartości null.

Dla typu zdefiniowanego w F # i użytego wyłącznie w języku F #, jedynym sposobem utworzenia wartości null przy użyciu biblioteki F # jest bezpośrednie użycie [unchecked. defaultof —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators-unchecked.html#defaultof) lub [Array. zeroCreate —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate). Jednak dla typu języka F #, który jest używany z innych języków .NET lub jeśli używasz tego typu z interfejsem API, który nie został zapisany w języku F #, takie jak .NET Framework, mogą wystąpić wartości null.

Można użyć `option` typu w F #, gdy można użyć zmiennej odwołania z wartością null w innym języku .NET. Zamiast wartości null, przy użyciu typu F # `option` , należy użyć wartości opcji, `None` Jeśli nie ma obiektu. Możesz użyć wartości opcji `Some(obj)` z obiektem, `obj` gdy istnieje obiekt. Aby uzyskać więcej informacji, zobacz [Opcje](../options.md). Należy zauważyć, że nadal można spakować `null` wartość do opcji, jeśli, na `Some x` , `x` ma być `null` . W związku z tym ważne jest, aby użyć, `None` gdy wartość jest `null` .

`null`Słowo kluczowe jest prawidłowym słowem kluczowym w języku F # i trzeba go używać podczas pracy z interfejsami api .NET Framework lub innymi interfejsami API, które są zapisywane w innym języku .NET. Dwie sytuacje, w których może być wymagana wartość null, są wywoływane w przypadku wywołania interfejsu API platformy .NET i przekazania wartości null jako argumentu oraz podczas interpretowania wartości zwracanej lub parametru wyjściowego z wywołania metody .NET.

Aby przekazać wartość null do metody .NET, należy po prostu użyć `null` słowa kluczowego w kodzie wywołującym. Pokazano to w poniższym przykładzie kodu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Aby interpretować wartość null, która jest uzyskiwana z metody .NET, należy użyć dopasowania wzorca, jeśli jest to możliwe. Poniższy przykład kodu pokazuje, jak używać dopasowywania wzorców do interpretowania wartości null, która jest zwracana z `ReadLine` podczas próby odczytu poza końcem strumienia wejściowego.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Wartości null dla typów F # można również generować w inny sposób, na przykład podczas używania `Array.zeroCreate` , które wywołania `Unchecked.defaultof` . Należy zachować ostrożność dzięki takiemu kodowi, aby zachować wartości null hermetyzowane. W bibliotece przeznaczonej tylko dla języka F # nie trzeba sprawdzać wartości null w każdej funkcji. Jeśli piszesz bibliotekę do międzyoperacyjności z innymi językami .NET, może być konieczne dodanie czeków dla parametrów wejściowych null i wyrzucanie `ArgumentNullException` , podobnie jak w języku C# lub Visual Basic kodzie.

Możesz użyć poniższego kodu, aby sprawdzić, czy arbitralna wartość jest równa null.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Zobacz też

- [Wartości](index.md)
- [Wyrażenia dopasowania](../match-expressions.md)
