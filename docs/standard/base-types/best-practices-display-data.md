---
title: Najlepsze rozwiązania dotyczące wyświetlania i utrwalania sformatowanych danych w programie .NET
description: Dowiedz się, jak efektywnie wyświetlać i utrzymywać dane liczbowe i daty w aplikacjach .NET.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 83a491f6c843225c6242a343fe4132c2ce7caa74
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403627"
---
# <a name="best-practices-for-displaying-and-persisting-formatted-data"></a>Najlepsze rozwiązania dotyczące wyświetlania i utrwalania sformatowanych danych

W tym artykule opisano, jak sformatowane dane, takie jak dane liczbowe oraz dane daty i godziny, są obsługiwane na potrzeby wyświetlania i przechowywania.

Podczas tworzenia przy użyciu platformy .NET należy użyć formatowania z uwzględnieniem kultury, aby wyświetlić dane niebędące ciągami, takie jak liczby i daty, w interfejsie użytkownika. Używaj formatowania z [kulturą niezmienną](xref:System.Globalization.CultureInfo.InvariantCulture) , aby utrwalać dane niebędące ciągami w postaci ciągów. Nie używaj formatowania z uwzględnieniem kultury, aby zachować dane liczbowe lub daty i godziny w postaci ciągu.

## <a name="displaying-formatted-data"></a>Wyświetlanie sformatowanych danych

W przypadku wyświetlania danych niebędących ciągami, takich jak liczby i daty i godziny, sformatuj je przy użyciu ustawień kultury użytkownika. Domyślnie następujące wszystkie używają bieżącej kultury wątku w operacjach formatowania:

- Ciągi interpolowane obsługiwane przez kompilatory [C#](../../csharp/language-reference/tokens/interpolated.md) i [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) .
- Operacje łączenia ciągów wykorzystujące operatory łączenia [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation) lub [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) lub bezpośrednio wywołujące <xref:System.String.Concat%2A?displayProperty=nameWithType> metodę.
- <xref:System.String.Format%2A?displayProperty=nameWithType>Metoda.
- `ToString`Metody typów liczbowych i typów dat i godzin.

Aby jawnie określić, że ciąg powinien być sformatowany przy użyciu konwencji określonej kultury lub [niezmiennej kultury](xref:System.Globalization.CultureInfo.InvariantCulture), można wykonać następujące czynności:

- Korzystając z <xref:System.String.Format%2A?displayProperty=nameWithType> metod i `ToString` , wywołaj Przeciążenie, które ma `provider` parametr, taki jak <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> lub <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> , i przekaż go <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> właściwości, <xref:System.Globalization.CultureInfo> wystąpienie, które reprezentuje pożądaną kulturę lub <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> Właściwość.

- W przypadku łączenia ciągów nie Zezwalaj kompilatorowi na wykonywanie jakichkolwiek niejawnych konwersji. Zamiast tego należy wykonać jawną konwersję, wywołując `ToString` Przeciążenie z `provider` parametrem. Na przykład kompilator niejawnie używa bieżącej kultury podczas konwertowania <xref:System.Double> wartości na ciąg w poniższym kodzie:

  [!code-csharp[Implicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#1)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#1)]

  Zamiast tego można jawnie określić kulturę, której konwencje formatowania są używane w konwersji, wywołując <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType> metodę, tak jak w poniższym kodzie:

  [!code-csharp[Explicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#2)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#2)]

- W przypadku interpolacji ciągów zamiast przypisywania do wystąpienia ciągu interpolowanego <xref:System.String> , należy przypisać go do <xref:System.FormattableString> . Następnie można wywołać <xref:System.FormattableString.ToString?displayProperty=nameWithType> metodę generującą ciąg wynikowy, który odzwierciedla konwencje bieżącej kultury, lub wywołać <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> metodę, aby utworzyć ciąg wynikowy, który odzwierciedla konwencje określonej kultury. Możesz również przekazać ciąg formatu do metody statycznej, <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> Aby utworzyć ciąg wynikowy, który odzwierciedla konwencje niezmiennej kultury. To podejście pokazano w poniższym przykładzie. (Dane wyjściowe z przykładu odzwierciedlają bieżącą kulturę en-US).

  [!code-csharp[String interpolation](./snippets/best-practices-strings/csharp/formattable/Program.cs)]
  [!code-vb[String interpolation](./snippets/best-practices-strings/vb/formattable/Program.vb)]

## <a name="persisting-formatted-data"></a>Utrwalanie sformatowanych danych

Dane niebędące ciągami mogą być utrwalane jako dane binarne lub dane sformatowane. Jeśli zdecydujesz się zapisać ją jako sformatowane dane, należy wywołać Przeciążenie metody formatowania, które zawiera `provider` parametr i przekazać go do <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> właściwości. Kultura niezmienna zapewnia spójny format sformatowanych danych, które są niezależne od kultury i maszyny. W przeciwieństwie do utrwalania danych, które są formatowane przy użyciu kultur innych niż kultura niezmienna, ma wiele ograniczeń:

- Dane mogą być bezużyteczne, jeśli są pobierane w systemie, który ma inną kulturę, lub jeśli użytkownik bieżącego systemu zmienia bieżącą kulturę i próbuje pobrać dane.
- Właściwości kultury na określonym komputerze mogą różnić się od wartości standardowych. W dowolnym momencie użytkownik może dostosować ustawienia wyświetlania z uwzględnieniem kultury. W związku z tym sformatowane dane zapisane w systemie mogą nie zostać odczytane, gdy użytkownik dostosowuje ustawienia kulturowe. Przenośność sformatowanych danych między komputerami może być jeszcze bardziej ograniczona.
- Międzynarodowe, regionalne lub krajowe standardy, które regulują formatowanie liczb lub dat i godzin zmiany czasu, i te zmiany są włączane do aktualizacji systemu operacyjnego Windows. W przypadku zmiany Konwencji formatowania dane sformatowane przy użyciu poprzednich Konwencji mogą stać się nieczytelne.

Poniższy przykład ilustruje ograniczoną przenośność, która wynika z używania formatowania z uwzględnieniem kultury do utrwalania danych. Przykład zapisuje tablicę wartości daty i godziny do pliku. Są one sformatowane przy użyciu Konwencji kultury angielskiej (Stany Zjednoczone). Gdy aplikacja zmieni bieżącą kulturę wątku na francuski (Szwajcaria), próbuje odczytać zapisane wartości przy użyciu Konwencji formatowania bieżącej kultury. Próba odczytania dwóch elementów danych zgłasza <xref:System.FormatException> wyjątek, a tablica dat zawiera teraz dwa niepoprawne elementy, które są równe <xref:System.DateTime.MinValue> .

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

Jeśli jednak zastąpisz <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> Właściwość <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> w wywołaniach do <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> i <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> , utrwalone dane daty i godziny zostaną pomyślnie przywrócone, ponieważ następujące dane wyjściowe pokazują:

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```
