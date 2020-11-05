---
title: Porównywanie ciągów w programie .NET
description: Przeczytaj informacje o metodach porównywania ciągów w programie .NET. Dowiedz się więcej o metodach Compare, CompareOrdinal, CompareTo, StartsWith, EndsWith, Equals, IndexOf, & LastIndexOf.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: 0efad4364d7d0070dd9c755234975e11ad524fbd
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400738"
---
# <a name="compare-strings-in-net"></a>Porównywanie ciągów w programie .NET

Platforma .NET udostępnia kilka metod porównywania wartości ciągów. W poniższej tabeli wymieniono i opisano metody porównywania wartości.

|Nazwa metody|Zastosowanie|
|-----------------|---------|
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|Porównuje wartości dwóch ciągów. Zwraca wartość całkowitą.|
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|Porównuje dwa ciągi bez względu na lokalną kulturę. Zwraca wartość całkowitą.|
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|Porównuje bieżący obiekt ciągu z innym ciągiem. Zwraca wartość całkowitą.|
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|Określa, czy ciąg rozpoczyna się ciągiem. Zwraca wartość logiczną.|
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|Określa, czy ciąg jest zakończony ciągiem zakończonym ciągiem. Zwraca wartość logiczną.|
|<xref:System.String.Contains%2A?displayProperty=nameWithType>|Określa, czy znak lub ciąg występuje w innym ciągu. Zwraca wartość logiczną.|
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|Określa, czy dwa ciągi są takie same. Zwraca wartość logiczną.|
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|Zwraca pozycję indeksu znaku lub ciągu, rozpoczynając od początku badanego ciągu. Zwraca wartość całkowitą.|
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|Zwraca pozycję indeksu znaku lub ciągu, rozpoczynając od końca badanego ciągu. Zwraca wartość całkowitą.|

## <a name="compare-method"></a>Compare — metoda

Metoda statyczna <xref:System.String.Compare%2A?displayProperty=nameWithType> zapewnia dokładny sposób porównywania dwóch ciągów. Ta metoda ma świadomość kulturową. Ta funkcja służy do porównywania dwóch ciągów lub podciągów dwóch ciągów. Ponadto przeciążenia są zapewnione w odniesieniu do wielkości liter i wariancji kulturowej. W poniższej tabeli przedstawiono trzy wartości całkowite, które ta metoda może zwrócić.

|Wartość zwracana|Warunek|
|------------------|---------------|
|Ujemna liczba całkowita|Pierwszy ciąg poprzedza drugi ciąg w kolejności sortowania.<br /><br /> -lub-<br /><br /> Pierwszy ciąg to `null` .|
|0|Pierwszy ciąg i drugi ciąg są równe.<br /><br /> -lub-<br /><br /> Oba ciągi są `null` .|
|Dodatnia liczba całkowita<br /><br /> -lub-<br /><br /> 1|Pierwszy ciąg jest zgodny z drugim ciągiem w kolejności sortowania.<br /><br /> -lub-<br /><br /> Drugi ciąg znaków to `null` .|

> [!IMPORTANT]
> <xref:System.String.Compare%2A?displayProperty=nameWithType>Metoda jest przeznaczona głównie do użycia podczas porządkowania i sortowania ciągów. Nie należy używać <xref:System.String.Compare%2A?displayProperty=nameWithType> metody do testowania pod kątem równości (oznacza to, że jawne szukanie zwracanej wartości 0 bez względu na to, czy jeden ciąg jest mniejszy od drugiego). Zamiast tego, aby określić, czy dwa ciągi są równe, użyj <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> metody.

 W poniższym przykładzie zastosowano <xref:System.String.Compare%2A?displayProperty=nameWithType> metodę, aby określić względne wartości dwóch ciągów.

 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]

 Ten przykład jest wyświetlany w `-1` konsoli programu.

 Poprzedni przykład jest domyślnie uwzględniany w kulturze. Aby wykonać Porównywanie ciągów niewrażliwych na kulturę, Użyj przeciążenia <xref:System.String.Compare%2A?displayProperty=nameWithType> metody, która pozwala określić kulturę do użycia przez dostarczenie parametru *kultury* . Aby zapoznać się z przykładem, który ilustruje sposób użycia <xref:System.String.Compare%2A?displayProperty=nameWithType> metody do wykonywania porównania niewrażliwego na kulturę, zobacz [porównanie ciągów nieuwzględniających kulturowo](../globalization-localization/performing-culture-insensitive-string-comparisons.md).

## <a name="compareordinal-method"></a>CompareOrdinal, Metoda

<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>Metoda porównuje dwa obiekty String bez rozważania lokalnej kultury. Wartości zwracane tej metody są identyczne z wartościami zwracanymi przez `Compare` metodę w poprzedniej tabeli.

> [!IMPORTANT]
> <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>Metoda jest przeznaczona głównie do użycia podczas porządkowania i sortowania ciągów. Nie należy używać <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> metody do testowania pod kątem równości (oznacza to, że jawne szukanie zwracanej wartości 0 bez względu na to, czy jeden ciąg jest mniejszy od drugiego). Zamiast tego, aby określić, czy dwa ciągi są równe, użyj <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> metody.

 Poniższy przykład używa `CompareOrdinal` metody do porównywania wartości dwóch ciągów.

 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]

 Ten przykład jest wyświetlany w `-32` konsoli programu.

## <a name="compareto-method"></a>CompareTo, Metoda

<xref:System.String.CompareTo%2A?displayProperty=nameWithType>Metoda porównuje ciąg, który bieżący obiekt ciągu hermetyzuje do innego ciągu lub obiektu. Wartości zwracane tej metody są identyczne z wartościami zwracanymi przez <xref:System.String.Compare%2A?displayProperty=nameWithType> metodę w poprzedniej tabeli.

> [!IMPORTANT]
> <xref:System.String.CompareTo%2A?displayProperty=nameWithType>Metoda jest przeznaczona głównie do użycia podczas porządkowania i sortowania ciągów. Nie należy używać <xref:System.String.CompareTo%2A?displayProperty=nameWithType> metody do testowania pod kątem równości (oznacza to, że jawne szukanie zwracanej wartości 0 bez względu na to, czy jeden ciąg jest mniejszy od drugiego). Zamiast tego, aby określić, czy dwa ciągi są równe, użyj <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> metody.

 W poniższym przykładzie zastosowano <xref:System.String.CompareTo%2A?displayProperty=nameWithType> metodę, aby porównać `string1` obiekt z `string2` obiektem.

 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]

 Ten przykład jest wyświetlany w `-1` konsoli programu.

 Wszystkie przeciążenia <xref:System.String.CompareTo%2A?displayProperty=nameWithType> metody domyślnie wykonują porównania uwzględniające kulturę i wielkość liter. Nie są dostarczane żadne przeciążenia tej metody, które umożliwiają wykonanie porównania niewrażliwego na kulturę. W przypadku przejrzystości kodu zalecamy użycie `String.Compare` metody zamiast tego, określając <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> dla operacji zależnych od kultury lub <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> dla operacji niewrażliwych na kulturę. Aby zapoznać się z przykładami, które pokazują, jak używać `String.Compare` metody do wykonywania porównań zarówno z uwzględnieniem kultury, jak i bez uwzględniania kultury, zobacz [wykonywanie porównań ciągów Culture-Insensitive](../globalization-localization/performing-culture-insensitive-string-comparisons.md).

## <a name="equals-method"></a>Equals — Metoda

<xref:System.String.Equals%2A?displayProperty=nameWithType>Metoda może łatwo określić, czy dwa ciągi są takie same. Ta metoda uwzględniania wielkości liter zwraca `true` wartość typu or `false` . Można go użyć z istniejącej klasy, jak pokazano w następnym przykładzie. W poniższym przykładzie zastosowano `Equals` metodę, aby określić, czy obiekt String zawiera frazę "Hello World".

 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]

 Ten przykład jest wyświetlany w `True` konsoli programu.

 Tej metody można również użyć jako metody statycznej. Poniższy przykład porównuje dwa obiekty String przy użyciu metody statycznej.

 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]

 Ten przykład jest wyświetlany w `True` konsoli programu.

## <a name="startswith-and-endswith-methods"></a>Metody StartsWith i EndsWith

Można użyć metody, <xref:System.String.StartsWith%2A?displayProperty=nameWithType> Aby określić, czy obiekt String zaczyna się od tych samych znaków, które obejmują inny ciąg. Ta metoda uwzględniania wielkości liter zwraca, `true` czy bieżący obiekt String zaczyna się od przekazaną i `false` czy nie. Poniższy przykład używa tej metody w celu ustalenia, czy obiekt String zaczyna się od "Hello".

 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]

 Ten przykład jest wyświetlany w `True` konsoli programu.

 <xref:System.String.EndsWith%2A?displayProperty=nameWithType>Metoda porównuje przekazaną ciąg z znakami, które istnieją na końcu bieżącego obiektu ciągu. Zwraca również wartość logiczną. Poniższy przykład sprawdza koniec ciągu przy użyciu `EndsWith` metody.

 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]

 Ten przykład jest wyświetlany w `False` konsoli programu.

## <a name="indexof-and-lastindexof-methods"></a>Metody IndexOf i LastIndexOf

Możesz użyć metody, <xref:System.String.IndexOf%2A?displayProperty=nameWithType> Aby określić pozycję pierwszego wystąpienia określonego znaku w ciągu. Ta metoda uwzględniająca wielkość liter rozpoczyna zliczanie od początku ciągu i zwraca pozycję podanego znaku przy użyciu indeksu rozpoczynającego się od zera. Jeśli nie można znaleźć znaku, zwracana jest wartość-1.

W poniższym przykładzie zastosowano `IndexOf` metodę w celu wyszukania pierwszego wystąpienia znaku " `l` " w ciągu.

 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]

 Ten przykład jest wyświetlany w `2` konsoli programu.

 <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>Metoda jest podobna do metody, `String.IndexOf` z tą różnicą, że zwraca pozycję ostatniego wystąpienia określonego znaku w ciągu. Jest uwzględniana wielkość liter i używa indeksu od zera.

 W poniższym przykładzie zastosowano `LastIndexOf` metodę w celu wyszukania ostatniego wystąpienia znaku " `l` " w ciągu.

 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]

 Ten przykład jest wyświetlany w `9` konsoli programu.

 Obie metody są przydatne, gdy są używane w połączeniu z <xref:System.String.Remove%2A?displayProperty=nameWithType> metodą. Możesz użyć albo `IndexOf` `LastIndexOf` metod, aby pobrać pozycję znaku, a następnie podać tę pozycję do `Remove` metody, aby usunąć znak lub Słowo zaczynające się od tego znaku.

## <a name="see-also"></a>Zobacz też

- [Najlepsze rozwiązania dotyczące używania ciągów w programie .NET](best-practices-strings.md)
- [Podstawowe operacje na ciągach](basic-string-operations.md)
- [Wykonywanie niezależnych od kultury operacji na ciągach](../globalization-localization/performing-culture-insensitive-string-operations.md)
- [Sortowanie tabel wagi](https://www.microsoft.com/download/details.aspx?id=10921) — używanych przez .NET Framework i .NET Core 1.0-3.1 w systemie Windows
- [Domyślna tabela elementów sortowania Unicode](https://www.unicode.org/Public/UCA/latest/allkeys.txt) — używana przez platformę .NET 5 na wszystkich platformach oraz przez platformę .NET Core w systemie Linux i macOS
