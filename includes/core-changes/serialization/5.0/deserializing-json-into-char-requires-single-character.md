---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844512"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="0bbdc-101">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="0bbdc-101">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="0bbdc-102">Gdy parametr type ma wartość <xref:System.Char> , argument ciągu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> musi zawierać pojedynczy znak do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-102">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0bbdc-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="0bbdc-103">Change description</span></span>

<span data-ttu-id="0bbdc-104">W poprzednich wersjach .NET, Jeśli przekażesz ciąg wieloznakowy do <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> i parametr typu jest <xref:System.Char> , deserializacja powiedzie się i tylko pierwszy znak jest deserializowany.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-104">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="0bbdc-105">W przypadku programu .NET 5,0 lub nowszego, gdy parametr typu jest <xref:System.Char> , przekazanie niczego poza ciągiem pojedynczym znakiem powoduje, że <xref:System.Text.Json.JsonException> ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-105">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a><span data-ttu-id="0bbdc-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0bbdc-106">Version introduced</span></span>

<span data-ttu-id="0bbdc-107">5,0</span><span class="sxs-lookup"><span data-stu-id="0bbdc-107">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0bbdc-108">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="0bbdc-108">Reason for change</span></span>

<span data-ttu-id="0bbdc-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analizuje tekst reprezentujący pojedynczą wartość JSON do wystąpienia typu określonego przez parametr typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="0bbdc-110">Analiza powinna zakończyć się powodzeniem tylko wtedy, gdy podany ładunek jest prawidłowy dla określonego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-110">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="0bbdc-111">Dla <xref:System.Char> typu wartości prawidłowy ładunek jest pojedynczym ciągiem znaków.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-111">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0bbdc-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="0bbdc-112">Recommended action</span></span>

<span data-ttu-id="0bbdc-113">Podczas analizowania ciągu do <xref:System.Char> typu przy użyciu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> , upewnij się, że ciąg zawiera pojedynczy znak.</span><span class="sxs-lookup"><span data-stu-id="0bbdc-113">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

#### <a name="category"></a><span data-ttu-id="0bbdc-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="0bbdc-114">Category</span></span>

<span data-ttu-id="0bbdc-115">Serializacja</span><span class="sxs-lookup"><span data-stu-id="0bbdc-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0bbdc-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0bbdc-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
