---
description: Break, instrukcja (odwołanie w C#)
title: Break, instrukcja (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134747"
---
# <a name="break-c-reference"></a>break (odwołanie w C#)

`break`Instrukcja kończy najbliższą otaczającą pętlę lub instrukcję [Switch](./switch.md) , w której występuje. Kontrolka jest przenoszona do instrukcji, która następuje po instrukcji zakończony (jeśli istnieje).

## <a name="example"></a>Przykład

W tym przykładzie Instrukcja warunkowa zawiera licznik, który powinien być liczony od 1 do 100; Jednakże `break` instrukcja kończy pętlę po 4 zliczenia.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Przykład

Ten przykład ilustruje użycie `break` w instrukcji [Switch](./switch.md) .

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

W przypadku wprowadzenia `4` danych wyjściowych będzie:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a>Przykład

W tym przykładzie `break` instrukcja jest używana do przerywania wewnętrznej pętli zagnieżdżonej i zwracania kontroli do pętli zewnętrznej. Formant jest zwracany _tylko_ jeden poziom w pętli zagnieżdżonych.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Przykład

W tym przykładzie `break` instrukcja jest używana tylko do rozbicia z bieżącej gałęzi podczas każdej iteracji pętli. Wystąpienia należące do samej pętli nie mają wpływ na `break` zagnieżdżoną instrukcję [Switch](./switch.md) .

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [przełącznika](./switch.md)
