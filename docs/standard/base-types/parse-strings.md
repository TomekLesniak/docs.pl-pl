---
title: Techniki analizowania ciągów w programie .NET
description: Dowiedz się więcej na temat różnych technik wyodrębniania części ciągu, takich jak String. Split, wyrażeń regularnych i String. substring.
ms.date: 10/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: de979b711a850bbb9ce91e1f1704d40a2f78f363
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2020
ms.locfileid: "93343364"
---
# <a name="extract-elements-from-a-string"></a>Wyodrębnij elementy z ciągu

W tym artykule opisano różne techniki wyodrębniania części ciągu.

- Użyj [metody Split](#stringsplit-method) , gdy podciągi mają być oddzielone znanym znakiem ograniczającym (lub znaków).
- [Wyrażenia regularne](#regular-expressions) są przydatne, gdy ciąg jest zgodny ze stałym wzorcem.
- Użyj [metod IndexOf i substring](#stringindexof-and-stringsubstring-methods) w połączeniu, gdy nie chcesz wyodrębnić *wszystkich* podciągów w ciągu.

## <a name="stringsplit-method"></a>String. Split — metoda

<xref:System.String.Split%2A?displayProperty=nameWithType> zapewnia kilku przeciążenia, aby pomóc w rozdzieleniu ciągu na grupę podciągów w oparciu o jeden lub więcej znaków, które określisz. Można ograniczyć całkowitą liczbę podciągów w wyniku końcowym, przyciąć znaki odstępu z podciągów lub wykluczyć puste podciągi.

W poniższych przykładach pokazano trzy różne przeciążenia `String.Split()` . Pierwszy przykład wywołuje <xref:System.String.Split(System.Char[])> Przeciążenie bez przechodzenia do żadnego znaku separatora. Gdy nie określisz żadnych ograniczników, program `String.Split()` używa domyślnych ograniczników, które są znakami odstępu, aby podzielić ciąg.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

Jak widać, znaki kropki ( `.` ) są uwzględniane w dwóch podciągach. Jeśli chcesz wykluczyć znaki okresowe, możesz dodać znak kropki jako dodatkowy znak ograniczający. W następnym przykładzie pokazano, jak to zrobić.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

Okresy są utracone z podciągów, ale teraz są uwzględniane dwa dodatkowe puste podciągi. Ten pusty podciąg reprezentuje podciąg między słowem a następującym okresem. Aby pominąć puste podciągi z tabeli wyników, można wywołać <xref:System.String.Split(System.Char[],System.StringSplitOptions)> Przeciążenie i określić <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> dla `options` parametru.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a>Wyrażenia regularne

Jeśli ciąg jest zgodny ze stałym wzorcem, można użyć wyrażenia regularnego, aby wyodrębnić i obsłużyć jego elementy. Na przykład jeśli ciągi przyjmują postać " *numer* *operandu* *numeru* ", można użyć [wyrażenia regularnego](regular-expressions.md) , aby wyodrębnić i obsłużyć elementy ciągu. Oto przykład:

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

Wzorzec wyrażenia regularnego `(\d+)\s+([-+*/])\s+(\d+)` jest zdefiniowany w następujący sposób:

|Wzorce|Opis|
|-------------|-----------------|
|`(\d+)`|Dopasowanie do co najmniej jednej cyfry dziesiętnej. Jest to pierwsza grupa przechwytywania.|
|`\s+`|Dopasowuje co najmniej jeden znak odstępu.|
|`([-+*/])`|Dopasowuje znak operatora arytmetycznego (+,-, * lub/). Jest to druga grupa przechwytywania.|
|`\s+`|Dopasowuje co najmniej jeden znak odstępu.|
|`(\d+)`|Dopasowanie do co najmniej jednej cyfry dziesiętnej. Jest to trzecia grupa przechwytywania.|

Możesz również użyć wyrażenia regularnego, aby wyodrębnić podciągi z ciągu na podstawie wzorca, a nie stałego zestawu znaków. Jest to typowy scenariusz, gdy występuje jeden z następujących warunków:

- Co najmniej jeden znak ogranicznika nie *zawsze* pełni rolę ogranicznika w <xref:System.String> wystąpieniu.

- Sekwencja i liczba znaków ogranicznika są zmienne lub nieznane.

Na przykład <xref:System.String.Split%2A> Metoda nie może być używana do dzielenia poniższego ciągu, ponieważ liczba `\n` znaków (nowego wiersza) jest zmienna i nie zawsze pełnią rolę ograniczników.

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

Wyrażenie regularne może łatwo podzielić ten ciąg, jak pokazano w poniższym przykładzie.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

Wzorzec wyrażenia regularnego `\[([^\[\]]+)\]` jest zdefiniowany w następujący sposób:

|Wzorce|Opis|
|-------------|-----------------|
|`\[`|Dopasowuje nawias otwierający.|
|`([^\[\]]+)`|Dopasowuje dowolny znak, który nie jest otwierającym lub zamykającym nawiasem jeden lub więcej razy. Jest to pierwsza grupa przechwytywania.|
|`\]`|Dopasowuje nawias zamykający.|

<xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>Metoda jest niemal identyczna z <xref:System.String.Split%2A?displayProperty=nameWithType> , z tą różnicą, że dzieli ciąg na podstawie wzorca wyrażenia regularnego zamiast stałego zestawu znaków. Na przykład poniższy przykład używa <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> metody, aby podzielić ciąg, który zawiera podciągi rozdzielone różnymi kombinacjami łączników i innych znaków.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

Wzorzec wyrażenia regularnego `\s-\s?[+*]?\s?-\s` jest zdefiniowany w następujący sposób:

|Wzorce|Opis|
|-------------|-----------------|
|`\s-`|Dopasowuje znak odstępu, po którym następuje łącznik.|
|`\s?`|Dopasowuje zero lub jeden znak odstępu.|
|`[+*]?`|Dopasowanie do zera lub jednego wystąpienia znaku + lub *.|
|`\s?`|Dopasowuje zero lub jeden znak odstępu.|
|`-\s`|Dopasowuje łącznik po którym następuje znak odstępu.|

## <a name="stringindexof-and-stringsubstring-methods"></a>Metody String. IndexOf i String. substring

Jeśli nie interesują Cię wszystkie podciągi w ciągu, być może wolisz pracować z jedną z metod porównywania ciągów, która zwraca indeks, w którym rozpoczyna się dopasowanie. Następnie można wywołać metodę, <xref:System.String.Substring%2A> Aby wyodrębnić żądany podciąg. Metody porównywania ciągów obejmują:

- <xref:System.String.IndexOf%2A>, która zwraca indeks (liczony od zera) pierwszego wystąpienia znaku lub ciągu w wystąpieniu ciągu.

- <xref:System.String.IndexOfAny%2A>, która zwraca indeks (liczony od zera) w bieżącym wystąpieniu ciągu pierwszego wystąpienia dowolnego znaku w tablicy znaków.

- <xref:System.String.LastIndexOf%2A>, która zwraca indeks (liczony od zera) ostatniego wystąpienia znaku lub ciągu w wystąpieniu ciągu.

- <xref:System.String.LastIndexOfAny%2A>, która zwraca indeks (liczony od zera) w bieżącym wystąpieniu ciągu ostatniego wystąpienia dowolnego znaku w tablicy znaków.

W poniższym przykładzie zastosowano <xref:System.String.IndexOf%2A> metodę, aby znaleźć okresy w ciągu. Następnie używa <xref:System.String.Substring%2A> metody do zwracania pełnych zdań.

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a>Zobacz też

- [Podstawowe operacje na ciągach w programie .NET](basic-string-operations.md)
- [Wyrażenia regularne .NET](regular-expressions.md)
- [Jak analizować ciągi przy użyciu ciągu. Split w C #](../../csharp/how-to/parse-strings-using-split.md)
