---
title: wyrażenie nameof — odwołanie w C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916780"
---
# <a name="nameof-expression-c-reference"></a>wyrażenie nameof (odwołanie w C#)

`nameof`Wyrażenie tworzy nazwę zmiennej, typu lub składowej jako stałą typu String:

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

Jak pokazano w powyższym przykładzie, w przypadku typu i przestrzeni nazw, wygenerowana nazwa zazwyczaj nie jest w [pełni kwalifikowana](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

W przypadku [identyfikatorów Verbatim](../tokens/verbatim.md) `@` znak nie jest częścią nazwy, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

`nameof`Wyrażenie jest oceniane w czasie kompilacji i nie ma wpływu na czas wykonywania.

Możesz użyć wyrażenia, `nameof` Aby zwiększyć łatwość obsługi kodu sprawdzania argumentów:

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

`nameof`Wyrażenie jest dostępne w języku C# 6 i nowszych.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia nameof](~/_csharplang/spec/expressions.md#nameof-expressions) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
