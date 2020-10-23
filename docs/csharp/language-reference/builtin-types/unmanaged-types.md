---
description: 'Informacje o typach niezarządzanych w języku C #'
title: Typy niezarządzane — odwołanie w C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 4374872af13c94e1a1af6b9f2c431f076c6f7dff
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471802"
---
# <a name="unmanaged-types-c-reference"></a>Typy niezarządzane (odwołanie w C#)

Typ jest **typem niezarządzanym** , jeśli jest dowolnego z następujących typów:

- `sbyte`,,,,, `byte` `short` ,,,, `ushort` `int` `uint` `long` `ulong` `char` `float` , `double` , `decimal` lub `bool`
- Dowolny typ [wyliczeniowy](enum.md)
- Dowolny typ [wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Dowolny zdefiniowany przez użytkownika typ [struktury](struct.md) , który zawiera pola tylko typy niezarządzane i, w języku C# 7,3 i wcześniejszych, nie jest typem skonstruowanym (typ, który zawiera co najmniej jeden argument typu)

Począwszy od języka C# 7,3, można użyć [ `unmanaged` ograniczenia](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) , aby określić, że parametr typu jest niewskaźnikiem typu niebędącego typem niedopuszczający wartości null.

Począwszy od języka C# 8,0, *skonstruowany* typ struktury, który zawiera pola typów niezarządzanych, również jest niezarządzany, jak pokazano w poniższym przykładzie:

[!code-csharp[unmanaged constructed types](snippets/shared/UnmanagedTypes.cs#ProgramExample)]

Struktura generyczna może być źródłem zarówno typów niezarządzanych, jak i niezarządzanych. W poprzednim przykładzie zdefiniowano strukturę generyczną `Coords<T>` i przedstawiono przykłady niezarządzanych typów skonstruowanych. Przykładem niezarządzanego typu jest `Coords<object>` . Nie jest ona zarządzana, ponieważ zawiera pola `object` typu, które nie są zarządzane. Jeśli chcesz, aby *wszystkie* skonstruowane typy były typami niezarządzanymi, użyj `unmanaged` ograniczenia w definicji generycznej struktury:

[!code-csharp[unmanaged constraint in type definition](snippets/shared/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [typy wskaźników](~/_csharplang/spec/unsafe-code.md#pointer-types) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Pamięć i typy związane z zakresem](../../../standard/memory-and-spans/index.md)
- [sizeof — Operator](../operators/sizeof.md)
- [stackalloc](../operators/stackalloc.md)
