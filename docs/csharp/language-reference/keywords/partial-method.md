---
description: Metoda częściowa — odwołanie w C#
title: Metoda częściowa — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: d6c433fd30f6ec51355bdefee90d815783487c1b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134383"
---
# <a name="partial-method-c-reference"></a>Metoda częściowa (odwołanie w C#)

Metoda częściowa ma swój podpis zdefiniowany w jednej części typu częściowego i jego implementacja zdefiniowana w innej części typu. Metody częściowe umożliwiają projektantom klas dostarczanie punktów zaczepienia metody, podobnie jak procedury obsługi zdarzeń, które deweloperzy mogą zdecydować się na wdrożenie lub nie. Jeśli deweloper nie poda implementacji, kompilator usuwa sygnaturę w czasie kompilacji. Poniższe warunki dotyczą metod częściowych:

- Sygnatury w obu częściach typu częściowego muszą być zgodne.

- Metoda musi zwracać typ void.

- Modyfikatory dostępu nie są dozwolone. Metody częściowe są niejawnie prywatne.

Poniższy przykład przedstawia metodę częściową zdefiniowaną w dwóch częściach klasy częściowej:

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

Aby uzyskać więcej informacji, zobacz [częściowe klasy i metody](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Typ częściowy](partial-type.md)
