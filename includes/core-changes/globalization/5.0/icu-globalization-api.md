---
ms.openlocfilehash: 02b5dc181abe384c1a5f47c042e475f67a0afe1c
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400808"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>Interfejsy API globalizacji korzystają z bibliotek ICU w systemie Windows

.NET 5,0 i nowsze wersje używają [międzynarodowych składników dla bibliotek Unicode (ICU)](http://site.icu-project.org/home) do obsługi funkcji globalizacji w przypadku uruchamiania w systemie Windows 10 maja 2019 Update lub nowszym.

#### <a name="change-description"></a>Zmień opis

W przypadku oprogramowania .NET Core 1,0-3,1 i .NET Framework 4 i nowszych biblioteki platformy .NET używają interfejsów API [obsługi języków (NLS)](/windows/win32/intl/national-language-support) dla funkcji globalizacji w systemie Windows. Na przykład funkcje NLS były używane do porównywania ciągów, uzyskiwania informacji o kulturze i wykonywania wielkich liter w odpowiedniej kulturze.

Począwszy od platformy .NET 5,0, jeśli aplikacja jest uruchomiona w systemie Windows 10 maja 2019 Update lub nowszym, biblioteki platformy .NET domyślnie używają interfejsów API [ICU](http://site.icu-project.org/home) globalizacji.

> [!NOTE]
> System Windows 10 maja 2019 Update i nowsze wersje są dostarczane z natywną biblioteką ICU. Jeśli środowisko uruchomieniowe platformy .NET nie może załadować ICU, zamiast tego używa środowiska NLS.

#### <a name="behavioral-differences"></a>Różnice w zachowaniu

Zmiany w aplikacji mogą być widoczne nawet wtedy, gdy nie są używane funkcje globalizacji. Ta sekcja zawiera kilka zmian w zachowaniu, które mogą się pojawić, ale również inne.

##### <a name="stringindexof"></a>String. IndexOf

Rozważmy następujący kod, który wywołuje, <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> Aby znaleźć indeks znaku nowego wiersza w ciągu.

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- W poprzednich wersjach programu .NET w systemie Windows, fragment kodu drukuje `6` .
- W przypadku programu .NET 5,0 i jego nowszych wersji w systemie Windows 19H1 i nowszych wersjach fragment zostanie wydrukowany `-1` .

Aby naprawić ten kod, przeprowadź wyszukiwanie porządkowe zamiast wyszukiwania z uwzględnieniem kultury, wywołaj <xref:System.String.IndexOf(System.String,System.StringComparison)> Przeciążenie i przekaż <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> jako argument.

Można uruchamiać reguły analizy kodu [CA1307: Określ StringComparison dla przejrzystości](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) i [CA1309: Użyj StringComparison porządkowej](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) , aby znaleźć te lokacje wywołań w kodzie.

Aby uzyskać więcej informacji, zobacz temat [zachowanie zmian w przypadku porównywania ciągów w programie .NET 5](../../../../docs/standard/base-types/string-comparison-net-5-plus.md)lub nowszym.

##### <a name="currency-symbol"></a>Symbol waluty

Rozważmy następujący kod, który sformatuje ciąg przy użyciu specyfikatora formatu waluty `C` . Kultura bieżącego wątku jest ustawiona na kulturę, która zawiera tylko język, a nie kraj.

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- W poprzednich wersjach programu .NET w systemie Windows wartością tekstową jest `"100,00 €"` .
- W programie .NET 5,0 i nowszych wersjach w systemie Windows 19H1 i nowszych wersjach wartość tekst to `"100,00 ¤"` , która używa symbolu waluty międzynarodowej zamiast euro. W ICU projekt jest, że walutą jest właściwość kraju lub regionu, a nie język.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w celu ujednolicenia. Zachowanie globalizacji sieci we wszystkich obsługiwanych systemach operacyjnych. Zapewnia również możliwość tworzenia przez aplikacje własnych bibliotek globalizacji, a nie zależą od bibliotek wbudowanych systemu operacyjnego.

#### <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0 (wersja zapoznawcza 4)

#### <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja. Jeśli jednak chcesz kontynuować korzystanie z interfejsów API globalizacji NLS, możesz ustawić [przełącznik czasu wykonywania](../../../../docs/core/run-time-config/globalization.md#nls) w celu przywrócenia tego zachowania. Aby uzyskać więcej informacji na temat dostępnych przełączników, zobacz artykuł [globalizacja i ICU platformy .NET](../../../../docs/standard/globalization-localization/globalization-icu.md) .

#### <a name="category"></a>Kategoria

- Podstawowe biblioteki platformy .NET
- Globalizacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Większość typów w <xref:System.Globalization?displayProperty=fullName> przestrzeni nazw
- <xref:System.Array.Sort%2A?displayProperty=fullName> (podczas sortowania tablicy ciągów)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (gdy elementy listy są ciągami)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (gdy klucze są ciągami)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (gdy klucze są ciągami)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (gdy zestaw zawiera ciągi)

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

-->
