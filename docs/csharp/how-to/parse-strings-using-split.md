---
title: Dzielenie ciągów przy użyciu ciągu. Split (Przewodnik C#)
description: Metoda Split zwraca tablicę ciągów podzieloną z zestawu ograniczników. Jest to prosty sposób wyodrębniania podciągów z ciągu.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 5361a3c60905edd19b180c5ddb14064a85f64337
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400503"
---
# <a name="how-to-separate-strings-using-stringsplit-in-c"></a>Jak rozdzielić ciągi przy użyciu ciągu. Split w C\#

<xref:System.String.Split%2A?displayProperty=nameWithType>Metoda tworzy tablicę podciągów, dzieląc ciąg wejściowy na podstawie co najmniej jednego ogranicznika. Ta metoda jest często najprostszym sposobem odseparowania ciągu na granicach wyrazów. Jest on również używany do dzielenia ciągów dla innych określonych znaków lub ciągów.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Poniższy kod dzieli wspólną frazę na tablicę ciągów dla każdego wyrazu.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

Każde wystąpienie znaku separatora generuje wartość w tablicy zwracanej. Kolejne znaki separatora tworzą pusty ciąg jako wartość w zwróconej tablicy. Można zobaczyć, jak w poniższym przykładzie jest tworzony pusty ciąg, który używa znaku spacji jako separatora.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

To zachowanie ułatwia formatowanie, takie jak pliki z wartościami rozdzielanymi przecinkami (CSV) reprezentujące dane tabelaryczne. Kolejne przecinki reprezentują pustą kolumnę.

Można przekazać opcjonalny parametr, <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> Aby wykluczyć wszelkie puste ciągi w zwróconej tablicy. Aby bardziej skomplikowane przetwarzanie zwróconej kolekcji było możliwe, można użyć [LINQ](../programming-guide/concepts/linq/index.md) do manipulowania sekwencją wyników.

<xref:System.String.Split%2A?displayProperty=nameWithType> może używać wielu znaków separatora.
Poniższy przykład używa spacji, przecinków, kropek, dwukropków i tabulatorów jako separatora znaków, które są przenoszone do <xref:System.String.Split%2A> tablicy.
Pętla u dołu kodu wyświetla każdy wyraz w zwracanej tablicy.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

Kolejne wystąpienia dowolnego separatora tworzą pusty ciąg w tablicy wyjściowej:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<xref:System.String.Split%2A?displayProperty=nameWithType> może przyjmować tablicę ciągów (sekwencje znaków, które działają jako separatory do analizowania ciągu docelowego, zamiast pojedynczych znaków).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a>Zobacz też

- [Wyodrębnij elementy z ciągu](../../standard/base-types/divide-up-strings.md)
- [Przewodnik programowania w języku C#](../programming-guide/index.md)
- [Ciągi](../programming-guide/strings/index.md)
- [Wyrażenia regularne .NET](../../standard/base-types/regular-expressions.md)
