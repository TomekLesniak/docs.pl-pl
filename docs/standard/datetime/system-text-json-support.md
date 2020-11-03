---
title: Obsługa elementów DateTime i DateTimeOffset w pliku System.Text.Json
description: Przegląd sposobu, w jaki typy DateTime i DateTimeOffset są obsługiwane w System.Text.Jsw bibliotece.
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 020e6903069da2c5d8761c86e890c4e9575a3fae
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188760"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Obsługa elementów DateTime i DateTimeOffset w pliku System.Text.Json

System.Text.Jsw bibliotece analizuje i zapisuje dane <xref:System.DateTime> oraz <xref:System.DateTimeOffset> wartości zgodnie z rozszerzonym profilem ISO 8601:-2019.
[Konwertery](xref:System.Text.Json.Serialization.JsonConverter%601) zapewniają obsługę niestandardową do serializacji i deserializacji za pomocą <xref:System.Text.Json.JsonSerializer> .
Obsługę niestandardową można również zaimplementować przy użyciu <xref:System.Text.Json.Utf8JsonReader> i <xref:System.Text.Json.Utf8JsonWriter> .

## <a name="support-for-the-iso-8601-12019-format"></a>Obsługa formatu ISO 8601-1:2019

<xref:System.Text.Json.JsonSerializer>,, <xref:System.Text.Json.Utf8JsonReader> <xref:System.Text.Json.Utf8JsonWriter> , I <xref:System.Text.Json.JsonElement> typy przeanalizują i zapisują <xref:System.DateTime> <xref:System.DateTimeOffset> reprezentacje, zgodnie z rozszerzonym profilem formatu ISO 8601-1:2019, na przykład 2019-07-26T16:59:57-05:00.

<xref:System.DateTime> i <xref:System.DateTimeOffset> można serializować dane przy użyciu <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Można je również zdeserializować przy użyciu <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Z opcjami domyślnymi <xref:System.DateTime> <xref:System.DateTimeOffset> reprezentacje wejściowe i tekstowe muszą być zgodne z rozszerzonym profilem ISO 8601-1:2019.
Próba deserializacji reprezentacji, które nie są zgodne z profilem, spowoduje <xref:System.Text.Json.JsonSerializer> wygenerowanie <xref:System.Text.Json.JsonException> :

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<xref:System.Text.Json.JsonDocument>Zapewnia strukturalny dostęp do zawartości ładunku JSON, w tym <xref:System.DateTime> i <xref:System.DateTimeOffset> reprezentacje. W poniższym przykładzie pokazano, jak w przypadku zbierania temperatury można obliczyć średnią temperaturę w poniedziałek:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Próba obliczenia średniej temperatury danego ładunku z niezgodnymi <xref:System.DateTime> reprezentacjami spowoduje <xref:System.Text.Json.JsonDocument> wygenerowanie <xref:System.FormatException> :

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

<xref:System.Text.Json.Utf8JsonWriter>Zapisy i dane niższego poziomu <xref:System.DateTime> <xref:System.DateTimeOffset> :

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> analizowanie <xref:System.DateTime> i <xref:System.DateTimeOffset> dane:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Próba odczytania niezgodnych formatów w programie <xref:System.Text.Json.Utf8JsonReader> spowoduje wygenerowanie <xref:System.FormatException> :

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Obsługa niestandardowa dla programu <xref:System.DateTime> i <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>W przypadku korzystania z <xref:System.Text.Json.JsonSerializer>

Jeśli chcesz, aby serializator wykonywał niestandardowe analizy lub formatowanie, możesz zaimplementować [niestandardowe konwertery](xref:System.Text.Json.Serialization.JsonConverter%601).
Oto kilka przykładów:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Korzystanie z `DateTime(Offset).Parse` i `DateTime(Offset).ToString`

Jeśli nie możesz określić formatów reprezentacji danych wejściowych <xref:System.DateTime> lub <xref:System.DateTimeOffset> tekstowych, możesz użyć `DateTime(Offset).Parse` metody z logiki odczytu konwertera. Umożliwia to korzystanie z programu. Rozległa pomoc techniczna w sieci na potrzeby analizowania różnych <xref:System.DateTime> <xref:System.DateTimeOffset> formatów i formatu tekstu, w tym ciągów z niestandardem ISO 8601 i formatów ISO 8601, które nie są zgodne z rozszerzonym profilem ISO 8601-1:2019. Ta metoda jest znacznie mniej wydajna niż użycie natywnej implementacji serializatora.

Do serializacji można użyć `DateTime(Offset).ToString` metody z logiki zapisu konwertera. Pozwala to pisać <xref:System.DateTime> i <xref:System.DateTimeOffset> wartości przy użyciu dowolnych [standardowych formatów daty i godziny](../base-types/standard-date-and-time-format-strings.md)oraz [niestandardowych formatów daty i godziny](../base-types/custom-date-and-time-format-strings.md).
Jest to również znacznie mniej wydajne niż użycie natywnej implementacji serializatora.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Podczas implementowania <xref:System.Text.Json.Serialization.JsonConverter%601> i `T` jest <xref:System.DateTime> `typeToConvert` parametr zawsze będzie `typeof(DateTime)` .
Parametr jest przydatny do obsługi przypadków polimorficznych i korzystania z typów ogólnych do uzyskania `typeof(T)` w sposób efektywny.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Korzystanie z <xref:System.Buffers.Text.Utf8Parser> i <xref:System.Buffers.Text.Utf8Formatter>

W logice konwertera można używać szybkich metod analizy i formatowania opartych na kodowaniu UTF-8 <xref:System.DateTime> , jeśli prezentacje wejściowe lub <xref:System.DateTimeOffset> tekstowe są zgodne z jednym z [ciągów standardowego formatu daty i godziny](../base-types/standard-date-and-time-format-strings.md)"R", "l", "O" lub "G", lub chcesz pisać według jednego z tych formatów. Jest to znacznie szybsze niż użycie `DateTime(Offset).Parse` i `DateTime(Offset).ToString` .

Ten przykład pokazuje niestandardowy konwerter, który serializować i deserializacji <xref:System.DateTime> wartości zgodnie z [formatem standardowym "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Standardowy format "R" będzie zawsze zawierać 29 znaków.
>
> Format "l" (mała litera "L") nie jest udokumentowany innymi [ciągami standardowego formatu daty i godziny](../base-types/standard-date-and-time-format-strings.md) , ponieważ jest obsługiwany tylko przez `Utf8Parser` typy i `Utf8Formatter` . Format jest małymi literami RFC 1123 (mała wersja formatu "R"), na przykład: "czwartek, 25 lip 2019 06:36:07 GMT".

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Używanie `DateTime(Offset).Parse` jako rezerwy do analizy natywnej serializatora

Jeśli zazwyczaj oczekujesz, że <xref:System.DateTime> dane wejściowe lub <xref:System.DateTimeOffset> zgodne z rozszerzonym profilem ISO 8601-1:2019, możesz użyć natywnej logiki analizy serializatora. Można również zaimplementować mechanizm rezerwowy tylko w przypadku.
Ten przykład pokazuje, że po niepowodzeniu analizy <xref:System.DateTime> reprezentacji tekstowej przy użyciu <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)> konwertera pomyślnie przeanalizuje dane przy użyciu <xref:System.DateTime.Parse(System.String)> .

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Podczas pisania przy użyciu <xref:System.Text.Json.Utf8JsonWriter>

Jeśli chcesz napisać niestandardową <xref:System.DateTime> lub <xref:System.DateTimeOffset> tekstową reprezentację za pomocą <xref:System.Text.Json.Utf8JsonWriter> , możesz sformatować swoją niestandardową reprezentację do <xref:System.String> ,, `ReadOnlySpan<Byte>` `ReadOnlySpan<Char>` , lub <xref:System.Text.Json.JsonEncodedText> , przekazać ją do odpowiedniej <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType> lub <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType> metody.

Poniższy przykład pokazuje, jak format niestandardowy <xref:System.DateTime> można utworzyć za pomocą <xref:System.DateTime.ToString(System.String,System.IFormatProvider)> , a następnie napisać przy użyciu <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> metody:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Podczas czytania z <xref:System.Text.Json.Utf8JsonReader>

Jeśli chcesz odczytać niestandardową <xref:System.DateTime> lub <xref:System.DateTimeOffset> tekstową reprezentację z <xref:System.Text.Json.Utf8JsonReader> , możesz pobrać wartość bieżącego tokenu JSON jako <xref:System.String> użycie <xref:System.Text.Json.Utf8JsonReader.GetString> , a następnie przeanalizować wartość przy użyciu logiki niestandardowej.

Poniższy przykład pokazuje, jak można pobrać niestandardową <xref:System.DateTimeOffset> reprezentację tekstową przy użyciu <xref:System.Text.Json.Utf8JsonReader.GetString> , a następnie przeanalizować ją przy użyciu <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)> :

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Profil rozszerzonego ISO 8601-1:2019 w System.Text.Jsna

### <a name="date-and-time-components"></a>Składniki daty i godziny

Profil rozszerzonego ISO 8601-1:2019 zaimplementowany w programie <xref:System.Text.Json> definiuje następujące składniki dla reprezentacji daty i godziny. Te składniki służą do definiowania różnych poziomów szczegółowości, które są obsługiwane podczas analizowania i formatowania <xref:System.DateTime> i <xref:System.DateTimeOffset> reprezentacji.

| Składnik       | Format                      | Opis                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Rok            | „yyyy”                      | 0001-9999                                                                       |
| Month (Miesiąc)           | „MM”                        | 01-12                                                                           |
| Dzień             | „dd”                        | 01-28, 01-29, 01-30, 01-31 w oparciu o miesiąc/rok                                  |
| Godzina            | „HH”                        | 00-23                                                                           |
| Minuta          | „mm”                        | 00-59                                                                           |
| Second          | „ss”                        | 00-59                                                                           |
| Druga część | „FFFFFFF”                   | Co najmniej jedna cyfra, maksymalnie 16 cyfr                                      |
| Przesunięcie czasu     | „K”                         | "Z" lub "(" + "/"-") gg": "mm"                                                |
| Czas częściowy    | "Gg": "mm": "SS [FFFFFFF]"     | Czas bez informacji o przesunięciu czasu UTC                                             |
| Pełna Data       | "yyyy'-'MM'-'dd"            | Data kalendarza                                                                   |
| Pełny czas       | "Częściowe time'K"           | Czas UTC dnia lub lokalny dzień z przesunięciem czasu między czasem lokalnym i czasem UTC |
| Data i godzina       | "" Pełna Data "t" "Pełny czas" " | Data i godzina kalendarzowa, np. 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Obsługa analizy

Następujące poziomy szczegółowości są zdefiniowane do analizy:

1. "Pełna Data"
    1. "yyyy'-'MM'-'dd"

2. "" Pełna Data "t" godzina "": "minuta" "
    1. "yyyy'-'MM'-'dd'T'HH": "mm"

3. "" Pełna Data "" t "" częściowe czas ""
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" ([specyfikator formatu sortowania ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier)
    2. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFF

4. "" Pełna Data "" t "godzina" ":" minuta "przesunięcie czasu" "
    1. "yyyy'-'MM'-'dd'T'HH": "mmZ"
    2. "yyyy'-'MM'-'dd'T'HH": "mm (" + "/"-") gg": "mm"

5. "Data i godzina"
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SSS"
    2. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFFZ"
    3. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" + "/"-") gg": "mm"
    4. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFF (' + '/'-') gg ': ' mm '

    Ten poziom szczegółowości jest zgodny ze standardem [RFC 3339](https://tools.ietf.org/html/rfc3339#section-5.6), powszechnie przyjętym profilem ISO 8601 używanym do zmieniania informacji o dacie i godzinie. Istnieje jednak kilka ograniczeń w System.Text.Jsw implementacji.

    - W dokumencie RFC 3339 nie określono maksymalnej liczby cyfr dziesiętnych, ale określa, że co najmniej jedna cyfra musi być zgodna z kropką, jeśli obecna jest sekcja ułamkowa sekunda. Implementacja w System.Text.Jszezwala na maksymalnie 16 cyfr (obsługa międzyoperacyjności z innymi językami programowania i strukturami), ale analizuje tylko pierwsze siedem. <xref:System.Text.Json.JsonException>Zostanie zgłoszony, jeśli podczas odczytywania i wystąpienia występuje więcej niż 16 cyfr sekund `DateTime` `DateTimeOffset` .
    - W dokumencie RFC 3339 znaki "T" i "Z" są odpowiednio "t" lub "z", ale zezwalają aplikacjom na ograniczenie obsługi tylko do wariantów wielkich liter. Implementacja w System.Text.Json wymaga "T" i "Z". <xref:System.Text.Json.JsonException>Zostanie wygenerowany, jeśli dane wejściowe zawierają "t" lub "z" podczas odczytywania `DateTime` i `DateTimeOffset` wystąpienia.
    - RFC 3339 określa, że sekcje daty i godziny są oddzielone znakiem "T", ale umożliwia aplikacjom rozdzielenie ich przez spację (""). System.Text.Json wymaga, aby sekcje daty i godziny zostały rozdzielone znakami "T". <xref:System.Text.Json.JsonException>Zostanie zgłoszony, jeśli ładunki wejściowe zawierają spację ("") podczas odczytywania `DateTime` i `DateTimeOffset` wystąpienia.

Jeśli istnieją ułamki dziesiętne dla sekund, musi zawierać co najmniej jedną cyfrę; `2019-07-26T00:00:00.` nie jest dozwolone.
Gdy dozwolone są maksymalnie 16 cyfr ułamkowych, analizowane są tylko pierwsze siedem. Wszystko, co jest traktowane jako zero.
Na przykład program `2019-07-26T00:00:00.1234567890` zostanie przeanalizowany tak, jakby był `2019-07-26T00:00:00.1234567` .
Jest to tak, aby zachować zgodność z <xref:System.DateTime> implementacją, która jest ograniczona do tego rozwiązania.

Sekundy przestępne nie są obsługiwane.

### <a name="support-for-formatting"></a>Obsługa formatowania

Następujące poziomy szczegółowości są zdefiniowane na potrzeby formatowania:

1. "" Pełna Data "" t "" częściowe czas ""
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" ([specyfikator formatu sortowania ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier)

        Służy do formatowania <xref:System.DateTime> bez ułamków sekund i bez informacji o przesunięciu.

    2. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFF

        Służy do formatowania <xref:System.DateTime> z ułamkami sekund, ale bez informacji o przesunięciu.

2. "Data i godzina"
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SSS"

        Służy do formatowania <xref:System.DateTime> bez ułamków sekund, ale z przesunięciem UTC.

    2. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFFZ"

        Służy do formatowania <xref:System.DateTime> z ułamkami sekund i przesunięciem czasu UTC.

    3. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" + "/"-") gg": "mm"

        Używane do formatowania <xref:System.DateTime> lub <xref:System.DateTimeOffset> bez ułamków sekund, ale z przesunięciem lokalnym.

    4. "yyyy'-'MM'-'dd'T'HH": "mm": "SS". " FFFFFFF (' + '/'-') gg ': ' mm '

        Służy do formatowania <xref:System.DateTime> lub <xref:System.DateTimeOffset> z ułamkami sekund i przesunięcia lokalnego.

    Ten poziom szczegółowości jest zgodny ze standardem [RFC 3339](https://tools.ietf.org/html/rfc3339#section-5.6).

Jeśli reprezentacja w [formacie rundy](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) <xref:System.DateTime> lub <xref:System.DateTimeOffset> ma końcowe zera w częściach sekund, <xref:System.Text.Json.JsonSerializer> a następnie <xref:System.Text.Json.Utf8JsonWriter> sformatuje reprezentację wystąpienia bez końcowych zer.
Na przykład wystąpienie, <xref:System.DateTime> którego reprezentacja [formatu okrężnego](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) ma wartość `2019-04-24T14:50:17.1010000Z` , zostanie sformatowane w taki sposób, jak `2019-04-24T14:50:17.101Z` <xref:System.Text.Json.JsonSerializer> i <xref:System.Text.Json.Utf8JsonWriter> .

Jeśli reprezentacja w [formacie rundy](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) <xref:System.DateTime> or <xref:System.DateTimeOffset> ma wszystkie zera w jego ułamkach sekund, <xref:System.Text.Json.JsonSerializer> a następnie <xref:System.Text.Json.Utf8JsonWriter> sformatuje reprezentację wystąpienia bez ułamków sekund.
Na przykład wystąpienie, <xref:System.DateTime> którego reprezentacja [formatu okrężnego](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) ma wartość `2019-04-24T14:50:17.0000000+02:00` , zostanie sformatowane w taki sposób, jak `2019-04-24T14:50:17+02:00` <xref:System.Text.Json.JsonSerializer> i <xref:System.Text.Json.Utf8JsonWriter> .

Obcinanie zer w cyfrach dziesiętnych umożliwia najmniejsze dane wyjściowe, które są konieczne, aby zachować informacje o liczbie, która ma być zapisywana.

Zapisywane są maksymalnie 7 cyfr dziesiętnych. Jest to zgodne z <xref:System.DateTime> implementacją, która jest ograniczona do tego rozwiązania.
