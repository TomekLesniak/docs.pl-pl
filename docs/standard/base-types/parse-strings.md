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
# <a name="extract-elements-from-a-string"></a><span data-ttu-id="02588-103">Wyodrębnij elementy z ciągu</span><span class="sxs-lookup"><span data-stu-id="02588-103">Extract elements from a string</span></span>

<span data-ttu-id="02588-104">W tym artykule opisano różne techniki wyodrębniania części ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-104">This article covers some different techniques for extracting parts of a string.</span></span>

- <span data-ttu-id="02588-105">Użyj [metody Split](#stringsplit-method) , gdy podciągi mają być oddzielone znanym znakiem ograniczającym (lub znaków).</span><span class="sxs-lookup"><span data-stu-id="02588-105">Use the [Split method](#stringsplit-method) when the substrings you want are separated by a known delimiting character (or characters).</span></span>
- <span data-ttu-id="02588-106">[Wyrażenia regularne](#regular-expressions) są przydatne, gdy ciąg jest zgodny ze stałym wzorcem.</span><span class="sxs-lookup"><span data-stu-id="02588-106">[Regular expressions](#regular-expressions) are useful when the string conforms to a fixed pattern.</span></span>
- <span data-ttu-id="02588-107">Użyj [metod IndexOf i substring](#stringindexof-and-stringsubstring-methods) w połączeniu, gdy nie chcesz wyodrębnić *wszystkich* podciągów w ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-107">Use the [IndexOf and Substring methods](#stringindexof-and-stringsubstring-methods) in conjunction when you don't want to extract *all* of the substrings in a string.</span></span>

## <a name="stringsplit-method"></a><span data-ttu-id="02588-108">String. Split — metoda</span><span class="sxs-lookup"><span data-stu-id="02588-108">String.Split method</span></span>

<span data-ttu-id="02588-109"><xref:System.String.Split%2A?displayProperty=nameWithType> zapewnia kilku przeciążenia, aby pomóc w rozdzieleniu ciągu na grupę podciągów w oparciu o jeden lub więcej znaków, które określisz.</span><span class="sxs-lookup"><span data-stu-id="02588-109"><xref:System.String.Split%2A?displayProperty=nameWithType> provides a handful of overloads to help you break up a string into a group of substrings based on one or more delimiting characters that you specify.</span></span> <span data-ttu-id="02588-110">Można ograniczyć całkowitą liczbę podciągów w wyniku końcowym, przyciąć znaki odstępu z podciągów lub wykluczyć puste podciągi.</span><span class="sxs-lookup"><span data-stu-id="02588-110">You can choose to limit the total number of substrings in the final result, trim white-space characters from substrings, or exclude empty substrings.</span></span>

<span data-ttu-id="02588-111">W poniższych przykładach pokazano trzy różne przeciążenia `String.Split()` .</span><span class="sxs-lookup"><span data-stu-id="02588-111">The following examples show three different overloads of `String.Split()`.</span></span> <span data-ttu-id="02588-112">Pierwszy przykład wywołuje <xref:System.String.Split(System.Char[])> Przeciążenie bez przechodzenia do żadnego znaku separatora.</span><span class="sxs-lookup"><span data-stu-id="02588-112">The first example calls the <xref:System.String.Split(System.Char[])> overload without passing any separator characters.</span></span> <span data-ttu-id="02588-113">Gdy nie określisz żadnych ograniczników, program `String.Split()` używa domyślnych ograniczników, które są znakami odstępu, aby podzielić ciąg.</span><span class="sxs-lookup"><span data-stu-id="02588-113">When you don't specify any delimiting characters, `String.Split()` uses default delimiters, which are white-space characters, to split up the string.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

<span data-ttu-id="02588-114">Jak widać, znaki kropki ( `.` ) są uwzględniane w dwóch podciągach.</span><span class="sxs-lookup"><span data-stu-id="02588-114">As you can see, the period characters (`.`) are included in two of the substrings.</span></span> <span data-ttu-id="02588-115">Jeśli chcesz wykluczyć znaki okresowe, możesz dodać znak kropki jako dodatkowy znak ograniczający.</span><span class="sxs-lookup"><span data-stu-id="02588-115">If you want to exclude the period characters, you can add the period character as an additional delimiting character.</span></span> <span data-ttu-id="02588-116">W następnym przykładzie pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="02588-116">The next example shows how to do this.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

<span data-ttu-id="02588-117">Okresy są utracone z podciągów, ale teraz są uwzględniane dwa dodatkowe puste podciągi.</span><span class="sxs-lookup"><span data-stu-id="02588-117">The periods are gone from the substrings, but now two extra empty substrings have been included.</span></span> <span data-ttu-id="02588-118">Ten pusty podciąg reprezentuje podciąg między słowem a następującym okresem.</span><span class="sxs-lookup"><span data-stu-id="02588-118">These empty substring represent the substring between the word and the period that follows it.</span></span> <span data-ttu-id="02588-119">Aby pominąć puste podciągi z tabeli wyników, można wywołać <xref:System.String.Split(System.Char[],System.StringSplitOptions)> Przeciążenie i określić <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> dla `options` parametru.</span><span class="sxs-lookup"><span data-stu-id="02588-119">To omit empty substrings from the resulting array, you can call the <xref:System.String.Split(System.Char[],System.StringSplitOptions)> overload and specify <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> for the `options` parameter.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a><span data-ttu-id="02588-120">Wyrażenia regularne</span><span class="sxs-lookup"><span data-stu-id="02588-120">Regular expressions</span></span>

<span data-ttu-id="02588-121">Jeśli ciąg jest zgodny ze stałym wzorcem, można użyć wyrażenia regularnego, aby wyodrębnić i obsłużyć jego elementy.</span><span class="sxs-lookup"><span data-stu-id="02588-121">If your string conforms to a fixed pattern, you can use a regular expression to extract and handle its elements.</span></span> <span data-ttu-id="02588-122">Na przykład jeśli ciągi przyjmują postać " *numer* *operandu* *numeru* ", można użyć [wyrażenia regularnego](regular-expressions.md) , aby wyodrębnić i obsłużyć elementy ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-122">For example, if strings take the form " *number* *operand* *number* ", you can use a [regular expression](regular-expressions.md) to extract and handle the string's elements.</span></span> <span data-ttu-id="02588-123">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="02588-123">Here's an example:</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

<span data-ttu-id="02588-124">Wzorzec wyrażenia regularnego `(\d+)\s+([-+*/])\s+(\d+)` jest zdefiniowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="02588-124">The regular expression pattern `(\d+)\s+([-+*/])\s+(\d+)` is defined like this:</span></span>

|<span data-ttu-id="02588-125">Wzorce</span><span class="sxs-lookup"><span data-stu-id="02588-125">Pattern</span></span>|<span data-ttu-id="02588-126">Opis</span><span class="sxs-lookup"><span data-stu-id="02588-126">Description</span></span>|
|-------------|-----------------|
|`(\d+)`|<span data-ttu-id="02588-127">Dopasowanie do co najmniej jednej cyfry dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="02588-127">Match one or more decimal digits.</span></span> <span data-ttu-id="02588-128">Jest to pierwsza grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="02588-128">This is the first capturing group.</span></span>|
|`\s+`|<span data-ttu-id="02588-129">Dopasowuje co najmniej jeden znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="02588-129">Match one or more white-space characters.</span></span>|
|`([-+*/])`|<span data-ttu-id="02588-130">Dopasowuje znak operatora arytmetycznego (+,-, \* lub/).</span><span class="sxs-lookup"><span data-stu-id="02588-130">Match an arithmetic operator sign (+, -, \*, or /).</span></span> <span data-ttu-id="02588-131">Jest to druga grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="02588-131">This is the second capturing group.</span></span>|
|`\s+`|<span data-ttu-id="02588-132">Dopasowuje co najmniej jeden znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="02588-132">Match one or more white-space characters.</span></span>|
|`(\d+)`|<span data-ttu-id="02588-133">Dopasowanie do co najmniej jednej cyfry dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="02588-133">Match one or more decimal digits.</span></span> <span data-ttu-id="02588-134">Jest to trzecia grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="02588-134">This is the third capturing group.</span></span>|

<span data-ttu-id="02588-135">Możesz również użyć wyrażenia regularnego, aby wyodrębnić podciągi z ciągu na podstawie wzorca, a nie stałego zestawu znaków.</span><span class="sxs-lookup"><span data-stu-id="02588-135">You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters.</span></span> <span data-ttu-id="02588-136">Jest to typowy scenariusz, gdy występuje jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="02588-136">This is a common scenario when either of these conditions occurs:</span></span>

- <span data-ttu-id="02588-137">Co najmniej jeden znak ogranicznika nie *zawsze* pełni rolę ogranicznika w <xref:System.String> wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="02588-137">One or more of the delimiter characters does not *always* serve as a delimiter in the <xref:System.String> instance.</span></span>

- <span data-ttu-id="02588-138">Sekwencja i liczba znaków ogranicznika są zmienne lub nieznane.</span><span class="sxs-lookup"><span data-stu-id="02588-138">The sequence and number of delimiter characters is variable or unknown.</span></span>

<span data-ttu-id="02588-139">Na przykład <xref:System.String.Split%2A> Metoda nie może być używana do dzielenia poniższego ciągu, ponieważ liczba `\n` znaków (nowego wiersza) jest zmienna i nie zawsze pełnią rolę ograniczników.</span><span class="sxs-lookup"><span data-stu-id="02588-139">For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\n` (newline) characters is variable, and they don't always serve as delimiters.</span></span>

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

<span data-ttu-id="02588-140">Wyrażenie regularne może łatwo podzielić ten ciąg, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="02588-140">A regular expression can split this string easily, as the following example shows.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

<span data-ttu-id="02588-141">Wzorzec wyrażenia regularnego `\[([^\[\]]+)\]` jest zdefiniowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="02588-141">The regular expression pattern `\[([^\[\]]+)\]` is defined like this:</span></span>

|<span data-ttu-id="02588-142">Wzorce</span><span class="sxs-lookup"><span data-stu-id="02588-142">Pattern</span></span>|<span data-ttu-id="02588-143">Opis</span><span class="sxs-lookup"><span data-stu-id="02588-143">Description</span></span>|
|-------------|-----------------|
|`\[`|<span data-ttu-id="02588-144">Dopasowuje nawias otwierający.</span><span class="sxs-lookup"><span data-stu-id="02588-144">Match an opening bracket.</span></span>|
|`([^\[\]]+)`|<span data-ttu-id="02588-145">Dopasowuje dowolny znak, który nie jest otwierającym lub zamykającym nawiasem jeden lub więcej razy.</span><span class="sxs-lookup"><span data-stu-id="02588-145">Match any character that is not an opening or a closing bracket one or more times.</span></span> <span data-ttu-id="02588-146">Jest to pierwsza grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="02588-146">This is the first capturing group.</span></span>|
|`\]`|<span data-ttu-id="02588-147">Dopasowuje nawias zamykający.</span><span class="sxs-lookup"><span data-stu-id="02588-147">Match a closing bracket.</span></span>|

<span data-ttu-id="02588-148"><xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>Metoda jest niemal identyczna z <xref:System.String.Split%2A?displayProperty=nameWithType> , z tą różnicą, że dzieli ciąg na podstawie wzorca wyrażenia regularnego zamiast stałego zestawu znaków.</span><span class="sxs-lookup"><span data-stu-id="02588-148">The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method is almost identical to <xref:System.String.Split%2A?displayProperty=nameWithType>, except that it splits a string based on a regular expression pattern instead of a fixed character set.</span></span> <span data-ttu-id="02588-149">Na przykład poniższy przykład używa <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> metody, aby podzielić ciąg, który zawiera podciągi rozdzielone różnymi kombinacjami łączników i innych znaków.</span><span class="sxs-lookup"><span data-stu-id="02588-149">For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

<span data-ttu-id="02588-150">Wzorzec wyrażenia regularnego `\s-\s?[+*]?\s?-\s` jest zdefiniowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="02588-150">The regular expression pattern `\s-\s?[+*]?\s?-\s` is defined like this:</span></span>

|<span data-ttu-id="02588-151">Wzorce</span><span class="sxs-lookup"><span data-stu-id="02588-151">Pattern</span></span>|<span data-ttu-id="02588-152">Opis</span><span class="sxs-lookup"><span data-stu-id="02588-152">Description</span></span>|
|-------------|-----------------|
|`\s-`|<span data-ttu-id="02588-153">Dopasowuje znak odstępu, po którym następuje łącznik.</span><span class="sxs-lookup"><span data-stu-id="02588-153">Match a white-space character followed by a hyphen.</span></span>|
|`\s?`|<span data-ttu-id="02588-154">Dopasowuje zero lub jeden znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="02588-154">Match zero or one white-space character.</span></span>|
|`[+*]?`|<span data-ttu-id="02588-155">Dopasowanie do zera lub jednego wystąpienia znaku + lub \*.</span><span class="sxs-lookup"><span data-stu-id="02588-155">Match zero or one occurrence of either the + or \* character.</span></span>|
|`\s?`|<span data-ttu-id="02588-156">Dopasowuje zero lub jeden znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="02588-156">Match zero or one white-space character.</span></span>|
|`-\s`|<span data-ttu-id="02588-157">Dopasowuje łącznik po którym następuje znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="02588-157">Match a hyphen followed by a white-space character.</span></span>|

## <a name="stringindexof-and-stringsubstring-methods"></a><span data-ttu-id="02588-158">Metody String. IndexOf i String. substring</span><span class="sxs-lookup"><span data-stu-id="02588-158">String.IndexOf and String.Substring methods</span></span>

<span data-ttu-id="02588-159">Jeśli nie interesują Cię wszystkie podciągi w ciągu, być może wolisz pracować z jedną z metod porównywania ciągów, która zwraca indeks, w którym rozpoczyna się dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="02588-159">If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins.</span></span> <span data-ttu-id="02588-160">Następnie można wywołać metodę, <xref:System.String.Substring%2A> Aby wyodrębnić żądany podciąg.</span><span class="sxs-lookup"><span data-stu-id="02588-160">You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want.</span></span> <span data-ttu-id="02588-161">Metody porównywania ciągów obejmują:</span><span class="sxs-lookup"><span data-stu-id="02588-161">The string comparison methods include:</span></span>

- <span data-ttu-id="02588-162"><xref:System.String.IndexOf%2A>, która zwraca indeks (liczony od zera) pierwszego wystąpienia znaku lub ciągu w wystąpieniu ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-162"><xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="02588-163"><xref:System.String.IndexOfAny%2A>, która zwraca indeks (liczony od zera) w bieżącym wystąpieniu ciągu pierwszego wystąpienia dowolnego znaku w tablicy znaków.</span><span class="sxs-lookup"><span data-stu-id="02588-163"><xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.</span></span>

- <span data-ttu-id="02588-164"><xref:System.String.LastIndexOf%2A>, która zwraca indeks (liczony od zera) ostatniego wystąpienia znaku lub ciągu w wystąpieniu ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-164"><xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="02588-165"><xref:System.String.LastIndexOfAny%2A>, która zwraca indeks (liczony od zera) w bieżącym wystąpieniu ciągu ostatniego wystąpienia dowolnego znaku w tablicy znaków.</span><span class="sxs-lookup"><span data-stu-id="02588-165"><xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.</span></span>

<span data-ttu-id="02588-166">W poniższym przykładzie zastosowano <xref:System.String.IndexOf%2A> metodę, aby znaleźć okresy w ciągu.</span><span class="sxs-lookup"><span data-stu-id="02588-166">The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string.</span></span> <span data-ttu-id="02588-167">Następnie używa <xref:System.String.Substring%2A> metody do zwracania pełnych zdań.</span><span class="sxs-lookup"><span data-stu-id="02588-167">It then uses the <xref:System.String.Substring%2A> method to return full sentences.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a><span data-ttu-id="02588-168">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02588-168">See also</span></span>

- [<span data-ttu-id="02588-169">Podstawowe operacje na ciągach w programie .NET</span><span class="sxs-lookup"><span data-stu-id="02588-169">Basic string operations in .NET</span></span>](basic-string-operations.md)
- [<span data-ttu-id="02588-170">Wyrażenia regularne .NET</span><span class="sxs-lookup"><span data-stu-id="02588-170">.NET regular expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="02588-171">Jak analizować ciągi przy użyciu ciągu. Split w C #</span><span class="sxs-lookup"><span data-stu-id="02588-171">How to parse strings using String.Split in C#</span></span>](../../csharp/how-to/parse-strings-using-split.md)
