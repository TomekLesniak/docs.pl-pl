---
title: Implementacja interfejsu jawnego — Przewodnik programowania w języku C#
description: Klasa może implementować interfejsy, które zawierają element członkowski o tej samej sygnaturze w języku C#. Implementacja jawna tworzy element członkowski klasy, który jest specyficzny dla jednego interfejsu.
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: a6ec328c08d1da84a11431d9400a094df8c72223
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303090"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementacja interfejsu jawnego (Przewodnik programowania w języku C#)

Jeśli [Klasa](../../language-reference/keywords/class.md) implementuje dwa interfejsy, które zawierają element członkowski o tym samym podpisie, a następnie wdrożenie tego elementu członkowskiego w klasie spowoduje, że oba interfejsy używają tego elementu członkowskiego jako ich implementacji. W poniższym przykładzie wszystkie wywołania do `Paint` wywołania tej samej metody. Ten pierwszy przykład definiuje typy:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

Poniższy przykład wywołuje metody:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Gdy dwa elementy członkowskie interfejsu nie wykonują tej samej funkcji, prowadzi do niepoprawnej implementacji jednego lub obu interfejsów. Istnieje możliwość jawnej implementacji elementu członkowskiego interfejsu — tworzenie składowej klasy, która jest wywoływana tylko przez interfejs i jest specyficzna dla tego interfejsu. Nazwij element członkowski klasy przy użyciu nazwy interfejsu i kropki. Na przykład:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

Element członkowski klasy `IControl.Paint` jest dostępny tylko za pomocą `IControl` interfejsu i `ISurface.Paint` jest dostępny tylko za pomocą `ISurface` . Obie implementacje metod są oddzielne i nie są dostępne bezpośrednio w klasie. Na przykład:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

Jawna implementacja służy również do rozwiązywania przypadków, gdy dwa interfejsy deklarują różne elementy członkowskie o tej samej nazwie, takie jak właściwość i metoda. Aby zaimplementować oba interfejsy, Klasa musi używać jawnej implementacji dla właściwości `P` albo metody lub obu tych metod `P` , aby uniknąć błędu kompilatora. Na przykład:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

Począwszy od [języka C# 8,0](../../whats-new/csharp-8.md#default-interface-methods), można zdefiniować implementację elementów członkowskich zadeklarowanych w interfejsie. Jeśli klasa dziedziczy implementację metody z interfejsu, ta metoda jest dostępna tylko za pośrednictwem typu interfejsu. Dziedziczony element członkowski nie jest wyświetlany jako część interfejsu publicznego. Poniższy przykład definiuje domyślną implementację metody interfejsu:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

Poniższy przykład wywołuje domyślną implementację:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Każda klasa implementująca `IControl` interfejs może przesłonić `Paint` metodę domyślną jako metodę publiczną lub jako jawną implementację interfejsu.

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Klasy i struktury](../classes-and-structs/index.md)
- [Interfejsy](./index.md)
- [Dziedziczenie](../classes-and-structs/inheritance.md)
