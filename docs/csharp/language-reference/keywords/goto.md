---
description: goto — instrukcja — odwołanie w C#
title: goto — instrukcja — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128429"
---
# <a name="goto-c-reference"></a>goto (odwołanie w C#)

`goto`Instrukcja przesyła bezpośrednio kontrolę programu do instrukcji oznaczonej etykietą.

Typowym zastosowaniem `goto` jest przeniesienie kontroli do określonej etykiety przypadku przełącznika lub etykiety domyślnej w `switch` instrukcji.

`goto`Instrukcja jest również przydatna do uzyskiwania z głęboko zagnieżdżonych pętli.

## <a name="example"></a>Przykład

Poniższy przykład demonstruje użycie `goto` w instrukcji [Switch](switch.md) .

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a>Przykład

Poniższy przykład ilustruje użycie polecenia `goto` , aby wydzielić z zagnieżdżonych pętli.

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [goto, instrukcja (C++)](/cpp/cpp/goto-statement-cpp)
