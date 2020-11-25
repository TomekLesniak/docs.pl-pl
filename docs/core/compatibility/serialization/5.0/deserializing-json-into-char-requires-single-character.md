---
title: 'Istotna zmiana: deserializacja wymaga ciągu pojedynczego znaku'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie JsonSerializer. deserializacji wymaga ciągu z pojedynczym znakiem.
ms.date: 10/18/2020
ms.openlocfilehash: 780f2928d776ecb6db9a7fc05a720e889eb363e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761651"
---
# <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="fa3ae-103">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="fa3ae-103">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="fa3ae-104">Gdy parametr type ma wartość <xref:System.Char> , argument ciągu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> musi zawierać pojedynczy znak do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-104">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

## <a name="change-description"></a><span data-ttu-id="fa3ae-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="fa3ae-105">Change description</span></span>

<span data-ttu-id="fa3ae-106">W poprzednich wersjach .NET, Jeśli przekażesz ciąg wieloznakowy do <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> i parametr typu jest <xref:System.Char> , deserializacja powiedzie się i tylko pierwszy znak jest deserializowany.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-106">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="fa3ae-107">W przypadku programu .NET 5,0 lub nowszego, gdy parametr typu jest <xref:System.Char> , przekazanie niczego poza ciągiem pojedynczym znakiem powoduje, że <xref:System.Text.Json.JsonException> ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-107">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="fa3ae-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="fa3ae-108">Version introduced</span></span>

<span data-ttu-id="fa3ae-109">5,0</span><span class="sxs-lookup"><span data-stu-id="fa3ae-109">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="fa3ae-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="fa3ae-110">Reason for change</span></span>

<span data-ttu-id="fa3ae-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analizuje tekst reprezentujący pojedynczą wartość JSON do wystąpienia typu określonego przez parametr typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="fa3ae-112">Analiza powinna zakończyć się powodzeniem tylko wtedy, gdy podany ładunek jest prawidłowy dla określonego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-112">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="fa3ae-113">Dla <xref:System.Char> typu wartości prawidłowy ładunek jest pojedynczym ciągiem znaków.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-113">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fa3ae-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="fa3ae-114">Recommended action</span></span>

<span data-ttu-id="fa3ae-115">Podczas analizowania ciągu do <xref:System.Char> typu przy użyciu <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> , upewnij się, że ciąg zawiera pojedynczy znak.</span><span class="sxs-lookup"><span data-stu-id="fa3ae-115">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fa3ae-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="fa3ae-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
