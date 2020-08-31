---
description: wyrażenie nameof — odwołanie w C#
title: wyrażenie nameof — odwołanie w C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 04109cde2a1f9146bf9bb44f301272808797ded0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118315"
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

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
