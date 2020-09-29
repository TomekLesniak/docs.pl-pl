---
description: Typ częściowy — odwołanie w C#
title: Typ częściowy — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4e73b34390143a2ac9b839e1da79b7894232c4b4
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91437885"
---
# <a name="partial-type-c-reference"></a>Typ częściowy (odwołanie w C#)

Definicje typu częściowego umożliwiają poddzielenie definicji klasy, struktury, interfejsu lub rekordu na wiele plików.

W *file1.cs*:

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

W *file2.cs* deklaracji:

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a>Uwagi

Dzielenie klasy, struktury lub interfejsu za pomocą kilku plików może być przydatne podczas pracy z dużymi projektami lub z automatycznie generowanym kodem, takim jak [Projektant formularzy systemu Windows](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time). Typ częściowy może zawierać [metodę częściową](partial-method.md). Aby uzyskać więcej informacji, zobacz [częściowe klasy i metody](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Modyfikatory](index.md)
- [Wprowadzenie do typów ogólnych](../../programming-guide/generics/index.md)
