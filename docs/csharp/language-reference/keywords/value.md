---
description: wartość kontekstowego słowa kluczowego — odwołanie w C#
title: wartość kontekstowego słowa kluczowego — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828919"
---
# <a name="value-c-reference"></a>value (odwołanie w C#)

Kontekstowe słowo kluczowe `value` jest używane w `set` metodzie dostępu w deklaracjach [Właściwości](../../programming-guide/classes-and-structs/properties.md) i [indeksatora](../../programming-guide/indexers/index.md) . Jest podobny do parametru wejściowego metody. Słowo `value` odwołuje się do wartości, którą kod klienta próbuje przypisać do właściwości lub indeksatora. W poniższym przykładzie `MyDerivedClass` ma właściwość o nazwie, `Name` która używa `value` parametru do przypisywania nowego ciągu do pola zapasowego `name` . Z punktu widzenia kodu klienta operacja jest zapisywana jako proste przypisanie.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Aby uzyskać więcej informacji, zobacz artykuły [Właściwości](../../programming-guide/classes-and-structs/properties.md) i [indeksatorów](../../programming-guide/indexers/index.md) .

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
