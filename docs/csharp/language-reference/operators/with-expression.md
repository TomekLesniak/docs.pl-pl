---
title: with Expression-C# — odwołanie
description: Dowiedz się więcej na temat wyrażenia with, które wykonuje nieniszczącą mutację rekordów C#
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: 8412dfe8663703d3b201fe98b5f4752da1b344cf
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556715"
---
# <a name="with-expression-c-reference"></a>with — wyrażenie (odwołanie w C#)

W języku C# 9,0 i nowszych, `with` wyrażenie tworzy kopię operandu [rekordu](../../whats-new/csharp-9.md#record-types) z określonymi właściwościami i polami zmodyfikowanymi:

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

Jak pokazano w powyższym przykładzie, użyj składni [inicjatora obiektów](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) , aby określić, które elementy członkowskie modyfikować i ich nowe wartości. W `with` wyrażeniu argument operacji po lewej stronie musi być typem rekordu.

Wynik `with` wyrażenia ma ten sam typ środowiska uruchomieniowego co operand wyrażenia, jak pokazano w poniższym przykładzie:

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

W przypadku elementu członkowskiego typu odwołania tylko odwołanie do wystąpienia jest kopiowane, gdy rekord jest kopiowany. Zarówno kopia, jak i rekord oryginalny mają dostęp do tego samego wystąpienia typu odwołania. Poniższy przykład ilustruje takie zachowanie:

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

Każdy typ rekordu ma *Konstruktor kopiujący*. Jest to Konstruktor z pojedynczym parametrem typu rekordu zawierającego. Kopiuje stan jego argumentu do nowego wystąpienia rekordu. Podczas obliczania `with` wyrażenia Konstruktor kopiujący jest wywoływany w celu utworzenia wystąpienia nowego rekordu na podstawie oryginalnego rekordu. Następnie nowe wystąpienie zostanie zaktualizowane zgodnie z określonymi modyfikacjami. Domyślnie Konstruktor kopiujący jest niejawny, czyli wygenerowany przez kompilator. Jeśli musisz dostosować semantykę kopiowania rekordów, jawnie Zadeklaruj konstruktor kopiujący z żądanym zachowaniem. Poniższy przykład aktualizuje poprzedni przykład z jawnym konstruktorem kopiującym. Nowe zachowanie kopiowania polega na skopiowaniu elementów listy zamiast odwołania do listy podczas kopiowania rekordu:

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje dotyczące [oferty funkcji Records](~/_csharplang/proposals/csharp-9.0/records.md):

- [`with` wyrażenia](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [Kopiowanie i klonowanie elementów członkowskich](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
