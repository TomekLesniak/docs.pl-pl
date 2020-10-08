---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844512"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku

Gdy parametr type ma wartość <xref:System.Char> , argument ciągu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> musi zawierać pojedynczy znak do deserializacji.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, Jeśli przekażesz ciąg wieloznakowy do <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> i parametr typu jest <xref:System.Char> , deserializacja powiedzie się i tylko pierwszy znak jest deserializowany.

W przypadku programu .NET 5,0 lub nowszego, gdy parametr typu jest <xref:System.Char> , przekazanie niczego poza ciągiem pojedynczym znakiem powoduje, że <xref:System.Text.Json.JsonException> ma zostać zgłoszony.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="reason-for-change"></a>Przyczyna zmiany

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analizuje tekst reprezentujący pojedynczą wartość JSON do wystąpienia typu określonego przez parametr typu ogólnego. Analiza powinna zakończyć się powodzeniem tylko wtedy, gdy podany ładunek jest prawidłowy dla określonego parametru typu ogólnego. Dla <xref:System.Char> typu wartości prawidłowy ładunek jest pojedynczym ciągiem znaków.

#### <a name="recommended-action"></a>Zalecana akcja

Podczas analizowania ciągu do <xref:System.Char> typu przy użyciu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> , upewnij się, że ciąg zawiera pojedynczy znak.

#### <a name="category"></a>Kategoria

Serializacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
