---
title: wyrażenie stackalloc — odwołanie w C#
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 4f20f3262b77cc2fe16480e53d13960e68d230b5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916668"
---
# <a name="stackalloc-expression-c-reference"></a>wyrażenie stackalloc (odwołanie w C#)

`stackalloc`Wyrażenie przydziela blok pamięci na stosie. Blok pamięci przydzielony przez stos utworzony podczas wykonywania metody jest automatycznie usuwany, gdy ta metoda zwraca. Nie można jawnie zwolnić pamięci przydzieloną z `stackalloc` . Przydzielony blok pamięci stosu nie podlega [wyrzucaniu elementów bezużytecznych](../../../standard/garbage-collection/index.md) i nie musi być przypięty za pomocą [ `fixed` instrukcji](../keywords/fixed-statement.md).

Wynik wyrażenia można przypisać `stackalloc` do zmiennej jednego z następujących typów:

- Począwszy od języka C# 7,2 <xref:System.Span%601?displayProperty=nameWithType> lub <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> , jak pokazano na poniższym przykładzie:

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  Nie trzeba używać [niebezpiecznego](../keywords/unsafe.md) kontekstu, gdy przypiszesz blok pamięci przydzielony przez stos do <xref:System.Span%601> <xref:System.ReadOnlySpan%601> zmiennej lub.

  Podczas pracy z tymi typami można użyć `stackalloc` wyrażenia w wyrażeniach [warunkowych](conditional-operator.md) lub przypisywania, jak pokazano na poniższym przykładzie:

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  Począwszy od języka C# 8,0, można użyć `stackalloc` wyrażenia wewnątrz innych wyrażeń za każdym razem <xref:System.Span%601> <xref:System.ReadOnlySpan%601> , gdy zmienna lub jest dozwolona, jak pokazano w poniższym przykładzie:

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > Zalecamy używanie <xref:System.Span%601> lub <xref:System.ReadOnlySpan%601> typy do pracy z przydzieloną pamięcią stosu, jeśli jest to możliwe.

- [Typ wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md), jak pokazano na poniższym przykładzie:

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  Jak pokazano w powyższym przykładzie, należy użyć `unsafe` kontekstu podczas pracy z typami wskaźników.

  W przypadku typów wskaźnika można użyć `stackalloc` wyrażenia tylko w deklaracji zmiennej lokalnej, aby zainicjować zmienną.

Ilość pamięci dostępnej na stosie jest ograniczona. W przypadku przydzielenia zbyt dużej ilości pamięci na stosie <xref:System.StackOverflowException> jest zgłaszany. Aby tego uniknąć, postępuj zgodnie z poniższymi regułami:

- Ogranicz ilość pamięci do przydzielenia `stackalloc` :

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  Ponieważ ilość pamięci dostępnej na stosie zależy od środowiska, w którym wykonywany jest kod, należy ją wyrównać podczas definiowania rzeczywistej wartości limitu.

- Unikaj używania `stackalloc` pętli wewnątrz. Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli.

Zawartość nowo przydzieloną pamięci jest niezdefiniowana. Należy ją zainicjować przed użyciem. Na przykład można użyć <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> metody, która ustawia wszystkie elementy na wartość domyślną typu `T` .

Począwszy od języka C# 7,3, można użyć składni inicjatora tablicy do zdefiniowania zawartości nowo przydzieloną pamięć. Poniższy przykład ilustruje różne sposoby, aby to zrobić:

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

W wyrażeniu `stackalloc T[E]` `T` musi być [typem niezarządzanym](../builtin-types/unmanaged-types.md) i `E` musi być wynikiem obliczenia nieujemnej wartości [int](../builtin-types/integral-numeric-types.md) .

## <a name="security"></a>Zabezpieczenia

Korzystanie z programu `stackalloc` automatycznie włącza funkcje wykrywania przepełnienia buforu w środowisku uruchomieniowym języka wspólnego (CLR). Jeśli wykryto przepełnienie buforu, proces zostaje zakończony jak najszybciej, aby zminimalizować prawdopodobieństwo wykonania złośliwego kodu.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [Alokacja stosu](~/_csharplang/spec/unsafe-code.md#stack-allocation) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md) i zapoznaj się z propozycją oferta funkcji [w przypadku `stackalloc` zagnieżdżonych kontekstów](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) .

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Operatory związane ze wskaźnikiem](pointer-related-operators.md)
- [Typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Pamięć i typy związane z zakresem](../../../standard/memory-and-spans/index.md)
- [DOS i stackalloc](https://vcsjones.dev/2020/02/24/stackalloc/)
