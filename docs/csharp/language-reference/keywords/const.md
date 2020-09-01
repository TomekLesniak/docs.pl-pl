---
description: const — słowo kluczowe — odwołanie w C#
title: const — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 312725c3a231f0ca766d5b99bf7d9308ddd634c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142092"
---
# <a name="const-c-reference"></a>const (odwołanie w C#)

Użyj `const` słowa kluczowego, aby zadeklarować pole stałe lub stałą lokalną. Pola stałe i zmienne lokalne nie są zmiennymi i nie mogą być modyfikowane. Stałe mogą być liczbami, wartościami logicznymi, ciągami lub odwołaniem o wartości null. Nie należy tworzyć stałej do reprezentowania informacji, które można zmienić w dowolnym momencie. Na przykład nie należy używać pola stałego do przechowywania ceny usługi, numeru wersji produktu ani nazwy marki firmy. Te wartości mogą ulec zmianie z upływem czasu, a ponieważ kompilatory propagują stałe, inne kod skompilowane z bibliotekami będzie musiały zostać ponownie skompilowane w celu wyświetlenia zmian. Zobacz również słowo kluczowe [ReadOnly](./readonly.md) . Przykład:

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a>Uwagi

Typ deklaracji stałej określa typ elementów członkowskich, które wprowadza deklaracja. Inicjator stałego lokalnego lub stałego pola musi być wyrażeniem stałym, które może być niejawnie konwertowane na typ docelowy.

Wyrażenie stałe jest wyrażeniem, które może być w pełni oceniane w czasie kompilacji. W związku z tym jedynymi możliwymi wartościami dla stałych typów odwołań są `string` i odwołania o wartości null.

Deklaracja stałej może deklarować wiele stałych, takich jak:

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

`static`Modyfikator nie jest dozwolony w deklaracji stałej.

Stała może uczestniczyć w wyrażeniu stałym w następujący sposób:

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> Słowo kluczowe [ReadOnly](./readonly.md) różni się od `const` słowa kluczowego. `const`Pole może być inicjowane tylko w deklaracji pola. `readonly`Pole może być inicjowane w deklaracji lub w konstruktorze. W związku z tym `readonly` pola mogą mieć różne wartości w zależności od użytego konstruktora. Ponadto mimo że `const` pole jest stałą czasu kompilacji, `readonly` pole może być używane dla stałych czasu wykonywania, jak w tym wierszu: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`

## <a name="example"></a>Przykład

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Przykład

W tym przykładzie pokazano, jak używać stałych jako zmiennych lokalnych.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [Modyfikatory](index.md)
- [readonly](./readonly.md)
