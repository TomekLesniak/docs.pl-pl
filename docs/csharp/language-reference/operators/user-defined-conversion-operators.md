---
title: Operatory konwersji zdefiniowane przez użytkownika — odwołanie w C#
description: Dowiedz się, jak definiować niestandardowe niejawne i jawne konwersje typów w języku C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
- explicit
- implicit
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: a0eb11d55ad9e9cccde1704ba4c5ae8acb609989
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916630"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Operatory konwersji zdefiniowane przez użytkownika (odwołanie w C#)

Typ zdefiniowany przez użytkownika może definiować niestandardową lub niejawną konwersję z lub do innego typu.

Konwersje niejawne nie wymagają wywoływania specjalnej składni i mogą wystąpić w różnych sytuacjach, na przykład w przypisaniach i metodach wywołania. Wstępnie zdefiniowane konwersje niejawne języka C# zawsze kończą się powodzeniem i nigdy nie generują wyjątku. Niejawne konwersje zdefiniowane przez użytkownika powinny również działać w ten sposób. Jeśli niestandardowa konwersja może zgłosić wyjątek lub utracić informacje, zdefiniuj ją jako konwersję jawną.

Konwersje zdefiniowane przez użytkownika nie są uwzględniane przez operatory [is](type-testing-and-cast.md#is-operator) i [as](type-testing-and-cast.md#as-operator) . Użyj [wyrażenia Cast](type-testing-and-cast.md#cast-expression) do wywołania jawnej konwersji zdefiniowanej przez użytkownika.

Użyj `operator` `implicit` `explicit` słów kluczowych i lub, aby zdefiniować odpowiednio niejawną lub jawną konwersję. Typ, który definiuje konwersję, musi być typem źródłowym lub typem docelowym tej konwersji. Konwersję między dwoma typami zdefiniowanymi przez użytkownika można zdefiniować w jeden z dwóch typów.

Poniższy przykład ilustruje sposób definiowania konwersji niejawnej i jawnej:

[!code-csharp[implicit an explicit conversions](snippets/shared/UserDefinedConversions.cs)]

Możesz również użyć `operator` słowa kluczowego do przeciążenia wstępnie zdefiniowanego operatora języka C#. Aby uzyskać więcej informacji, zobacz [przeciążanie operatora](operator-overloading.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Operatory konwersji](~/_csharplang/spec/classes.md#conversion-operators)
- [Konwersje zdefiniowane przez użytkownika](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Konwersje niejawne](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Konwersje jawne](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Przeładowanie operatora](operator-overloading.md)
- [Operatory testowania typu i rzutowania](type-testing-and-cast.md)
- [Rzutowanie i Konwersja typów](../../programming-guide/types/casting-and-type-conversions.md)
- [Wytyczne dotyczące projektowania — operatory konwersji](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [Jawne konwersje zdefiniowane przez użytkownika w języku C #](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
