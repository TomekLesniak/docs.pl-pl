---
title: Typy wartości null — odwołanie w C#
description: Dowiedz się więcej o typach wartości null języka C# i sposobach ich użycia
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 3ab2dff6b7399b0458a69d4498b2ebda24f6c5cc
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471838"
---
# <a name="nullable-value-types-c-reference"></a>Typy wartości null (odwołanie w C#)

*Typ wartości null* `T?` reprezentuje wszystkie wartości jego bazowego [typu wartości](value-types.md) `T` oraz dodatkową wartość [null](../keywords/null.md) . Na przykład można przypisać jedną z następujących trzech wartości do `bool?` zmiennej: `true` , `false` , lub `null` . Podstawowy typ wartości `T` nie może być samym typem wartości null.

> [!NOTE]
> W języku C# 8,0 wprowadzono funkcję typów referencyjnych dopuszczających wartość null. Aby uzyskać więcej informacji, zobacz [typy referencyjne dopuszczające wartość null](nullable-reference-types.md). Typy wartości null są dostępne począwszy od języka C# 2.

Każdy typ wartości null jest wystąpieniem <xref:System.Nullable%601?displayProperty=nameWithType> struktury ogólnej. Można odwołać się do typu wartości null z typem bazowym `T` w dowolnej z następujących metod zamiennych: `Nullable<T>` lub `T?` .

Typ wartości null jest zazwyczaj używany, gdy trzeba reprezentować niezdefiniowaną wartość bazowego typu wartości. Na przykład wartość logiczna lub `bool` zmienna może mieć wartość `true` lub `false` . Jednak w niektórych aplikacjach wartość zmiennej może być niezdefiniowana lub brakująca. Na przykład pole bazy danych może zawierać `true` lub lub `false` nie może zawierać żadnej wartości, czyli `NULL` . Możesz użyć `bool?` typu w tym scenariuszu.

## <a name="declaration-and-assignment"></a>Deklaracja i przypisanie

Ponieważ typ wartości jest niejawnie konwertowany do odpowiadającego typu wartości null, można przypisać wartość do zmiennej typu wartości null, tak jak w przypadku jego bazowego typu wartości. Możesz również przypisać `null` wartość. Przykład:

[!code-csharp[declare and assign](snippets/shared/NullableValueTypes.cs#Declaration)]

Wartość domyślna typu wartości null reprezentuje `null` , czyli to wystąpienie, którego <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> Właściwość zwraca `false` .

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Badanie wystąpienia typu wartości null

Począwszy od języka C# 7,0, można użyć [ `is` operatora ze wzorcem typu](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) do obu badań wystąpienie typu wartości null dla `null` i pobrać wartość typu podstawowego:

[!code-csharp-interactive[use pattern matching](snippets/shared/NullableValueTypes.cs#PatternMatching)]

Aby sprawdzać i pobierać wartość zmiennej typu wartości null, zawsze można użyć następujących właściwości tylko do odczytu:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> wskazuje, czy wystąpienie typu wartości null ma wartość jego typu podstawowego.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> Pobiera wartość typu podstawowego, jeśli <xref:System.Nullable%601.HasValue%2A> jest `true` . Jeśli <xref:System.Nullable%601.HasValue%2A> ma wartość `false` , <xref:System.Nullable%601.Value%2A> Właściwość zgłasza <xref:System.InvalidOperationException> .

Poniższy przykład używa właściwości, `HasValue` Aby sprawdzić, czy zmienna zawiera wartość przed wyświetleniem:

[!code-csharp-interactive[use HasValue](snippets/shared/NullableValueTypes.cs#HasValue)]

Możesz również porównać zmienną typu wartości null z `null` zamiast używać `HasValue` właściwości, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[use comparison with null](snippets/shared/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Konwersja z typu wartości null na typ podstawowy

Jeśli chcesz przypisać wartość typu wartości null do zmiennej typu wartości, która nie dopuszcza wartości null, może być konieczne określenie wartości, która ma zostać przypisana zamiast `null` . Użyj [ `??` operatora łączenia wartości null](../operators/null-coalescing-operator.md) , aby to zrobić (można również użyć <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> metody do tego samego celu):

[!code-csharp-interactive[?? operator](snippets/shared/NullableValueTypes.cs#NullCoalescing)]

Jeśli chcesz użyć [domyślnej](default-values.md) wartości bazowego typu wartości zamiast `null` , użyj <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> metody.

Można również jawnie rzutować typ wartości null na typ niedopuszczający wartości null, co ilustruje poniższy przykład:

[!code-csharp[explicit cast](snippets/shared/NullableValueTypes.cs#Cast)]

W czasie wykonywania, jeśli wartość typu wartości null to `null` , jawne rzutowanie zgłosi <xref:System.InvalidOperationException> .

Typ wartości niedopuszczający wartości null `T` jest niejawnie konwertowany na odpowiedni typ wartości null `T?` .

## <a name="lifted-operators"></a>Podniesione operatory

Wstępnie zdefiniowane [Operatory](../operators/index.md) jednoargumentowe i binarne lub wszelkie przeciążone operatory obsługiwane przez typ wartości `T` są również obsługiwane przez odpowiedni typ wartości null `T?` . Te operatory, znane także jako *zniesione operatory*, tworzą, `null` Jeśli jeden lub oba operandy są `null` ; w przeciwnym razie operator używa zawartych wartości argumentów operacji, aby obliczyć wynik. Przykład:

[!code-csharp[lifted operators](snippets/shared/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Dla `bool?` typu, wstępnie zdefiniowane `&` Operatory i `|` nie przestrzegają zasad opisanych w tej sekcji: wynik oceny operatora może być inny niż null, nawet jeśli jeden z operandów jest `null` . Aby uzyskać więcej informacji, zobacz sekcję [Operatory logiczne wartości null](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) w artykule [Operatory logiczne Boolean](../operators/boolean-logical-operators.md) .

W przypadku [operatorów porównania](../operators/comparison-operators.md) `<` , `>` , `<=` i `>=` , jeśli jeden lub oba operandy są `null` , wynikiem jest `false` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane. Nie należy zakładać, że ponieważ określone porównanie (na przykład `<=` ) zwraca `false` , odwrotne porównanie ( `>` ) zwraca wartość `true` . Poniższy przykład pokazuje, że 10 jest

- nie większe niż lub równe `null`
- nie mniejsze niż `null`

[!code-csharp-interactive[relational and equality operators](snippets/shared/NullableValueTypes.cs#ComparisonOperators)]

W przypadku [operatora równości](../operators/equality-operators.md#equality-operator-) `==` , jeśli oba operandy są `null` , wynikiem jest `true` , jeśli tylko jeden z operandów ma wartość, `null` wynik to `false` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane.

W przypadku [operatora nierówności](../operators/equality-operators.md#inequality-operator-) `!=` , jeśli oba operandy są `null` , wynikiem jest `false` , jeśli tylko jeden z operandów ma wartość, `null` wynik to `true` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane.

Jeśli istnieje [konwersja zdefiniowana przez użytkownika](../operators/user-defined-conversion-operators.md) między dwoma typami wartości, można także użyć tej samej konwersji między odpowiednimi typami wartości null.

## <a name="boxing-and-unboxing"></a>Pakowanie i rozpakowywanie

Wystąpienie typu wartości null `T?` jest [opakowane](../../programming-guide/types/boxing-and-unboxing.md) w następujący sposób:

- Jeśli <xref:System.Nullable%601.HasValue%2A> zwraca `false` , zostanie utworzone odwołanie o wartości null.
- Jeśli <xref:System.Nullable%601.HasValue%2A> zwraca `true` , odpowiadająca wartość bazowego typu wartości `T` jest opakowana, a nie wystąpieniem <xref:System.Nullable%601> .

Można Unbox wartość opakowaną typu wartości `T` do odpowiadającego typu wartości null `T?` , co ilustruje poniższy przykład:

[!code-csharp-interactive[boxing and unboxing](snippets/shared/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Jak zidentyfikować typ wartości null

Poniższy przykład pokazuje, jak ustalić, czy <xref:System.Type?displayProperty=nameWithType> wystąpienie reprezentuje skonstruowany typ wartości null, czyli <xref:System.Nullable%601?displayProperty=nameWithType> Typ z określonym parametrem typu `T` :

[!code-csharp-interactive[whether Type is nullable](snippets/shared/NullableValueTypes.cs#IsTypeNullable)]

Jak pokazano w przykładzie, należy użyć operatora [typeof](../operators/type-testing-and-cast.md#typeof-operator) do utworzenia <xref:System.Type?displayProperty=nameWithType> wystąpienia.

Aby określić, czy wystąpienie ma typ wartości null, nie należy używać <xref:System.Object.GetType%2A?displayProperty=nameWithType> metody, aby uzyskać <xref:System.Type> wystąpienie do przetestowania przy użyciu poprzedniego kodu. Gdy wywoływana jest <xref:System.Object.GetType%2A?displayProperty=nameWithType> Metoda w wystąpieniu typu wartości null, wystąpienie jest [opakowane](#boxing-and-unboxing) na <xref:System.Object> . Jako opakowanie niezerowego typu wartości null jest równoważne z opakowaniem wartości typu podstawowego, <xref:System.Object.GetType%2A> zwraca <xref:System.Type> wystąpienie reprezentujące typ podstawowy typu wartości null:

[!code-csharp-interactive[GetType example](snippets/shared/NullableValueTypes.cs#GetType)]

Ponadto nie należy używać operatora [is](../operators/type-testing-and-cast.md#is-operator) , aby określić, czy wystąpienie ma typ wartości null. Jak pokazano na poniższym przykładzie, nie można rozróżnić typów wystąpienia typu wartości null i jego wystąpienia podstawowego z `is` operatorem:

[!code-csharp-interactive[is operator example](snippets/shared/NullableValueTypes.cs#IsOperator)]

Możesz użyć kodu przedstawionego w poniższym przykładzie, aby określić, czy wystąpienie ma typ wartości null:

[!code-csharp-interactive[whether an instance is of a nullable type](snippets/shared/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> Metody opisane w tej sekcji nie mają zastosowania w przypadku [typów referencyjnych dopuszczających wartość null](nullable-reference-types.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Typy dopuszczające wartości null](~/_csharplang/spec/types.md#nullable-types)
- [Podniesione operatory](~/_csharplang/spec/expressions.md#lifted-operators)
- [Niejawne konwersje dopuszczające wartość null](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Jawne konwersje dopuszczające wartość null](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [Przenoszone operatory konwersji](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Co dokładnie ma znaczenie "zniesione"?](/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Typy referencyjne dopuszczające wartość null](nullable-reference-types.md)
