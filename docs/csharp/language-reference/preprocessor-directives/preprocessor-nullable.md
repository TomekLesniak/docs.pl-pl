---
description: '#Odwołanie do kodu w języku C#'
title: '#Odwołanie do kodu w języku C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099464"
---
# <a name="nullable-c-reference"></a>#nullable (odwołanie w C#)

`#nullable`Dyrektywa preprocesora ustawia *kontekst adnotacji dopuszczający wartość null* i *kontekst ostrzeżenia o wartości null*. Ta dyrektywa kontroluje, czy adnotacje dopuszczające wartość null mają wpływ, oraz czy są określone ostrzeżenia o wartości null. Każdy kontekst jest *wyłączony* lub *włączony*.

Oba konteksty można określić na poziomie projektu (poza kodem źródłowym C#). `#nullable`Dyrektywa kontroluje konteksty adnotacji i ostrzeżeń i ma pierwszeństwo przed ustawieniami na poziomie projektu. Dyrektywa ustawia konteksty, które kontroluje, dopóki inna dyrektywa przesłoni ją lub do końca pliku źródłowego.

Efekty dyrektyw są następujące:

- `#nullable disable`: Ustawia adnotacje dopuszczające wartość null i konteksty ostrzeżeń do *wyłączania*.
- `#nullable enable`: Ustawia do *włączenia* adnotację z dopuszczaniem wartości null i kontekstów ostrzeżeń.
- `#nullable restore`: Przywraca w ustawieniach projektu adnotację dopuszczającą wartość null i konteksty ostrzeżenia.
- `#nullable disable annotations`: Ustawia kontekst adnotacji dopuszczającej wartość null na *wyłączony*.
- `#nullable enable annotations`: Ustawia kontekst adnotacji dopuszczający wartość *null.*
- `#nullable restore annotations`: Przywraca kontekst adnotacji dopuszczający wartość null do ustawień projektu.
- `#nullable disable warnings`: Ustawia kontekst ostrzeżenia wartości null na *wyłączony*.
- `#nullable enable warnings`: Ustawia kontekst ostrzegawczy dopuszczający wartość *null.*
- `#nullable restore warnings`: Przywraca kontekst ostrzegawczy dopuszczający wartość null do ustawień projektu.

## <a name="see-also"></a>Zobacz także

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
