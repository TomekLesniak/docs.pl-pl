---
title: 'Istotna zmiana: serializacja zgłasza wyjątek, gdy parametr typu ma wartość null'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, w której metody serializacji JsonSerialize, które mają parametr typu, teraz zgłaszają wyjątek, gdy dla tego parametru jest przenoszona wartość null.
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761635"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="2e13e-103">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="2e13e-103">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="2e13e-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> , i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> przeciążenia, które mają parametr typu, <xref:System.Type> są teraz zgłaszane <xref:System.ArgumentNullException> za każdym razem, gdy `null` zostanie przesłany dla tego parametru.</span><span class="sxs-lookup"><span data-stu-id="2e13e-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a parameter of type <xref:System.Type> now throw an <xref:System.ArgumentNullException> whenever `null` is passed for that parameter.</span></span>

## <a name="change-description"></a><span data-ttu-id="2e13e-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="2e13e-105">Change description</span></span>

<span data-ttu-id="2e13e-106">W przypadku programu .NET Core 3,1,, <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads, które mają <xref:System.Type> parametr throw <xref:System.ArgumentNullException> gdy `null` jest przenoszona do `Type inputType` parametru, ale nie w przypadku, gdy `Object value` parametr jest również `null` .</span><span class="sxs-lookup"><span data-stu-id="2e13e-106">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="2e13e-107">Począwszy od platformy .NET 5,0, metody te *zawsze* generują <xref:System.ArgumentNullException> gdy `null` jest przenoszona dla <xref:System.Type> parametru.</span><span class="sxs-lookup"><span data-stu-id="2e13e-107">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="2e13e-108">Zachowanie w programie .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="2e13e-108">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="2e13e-109">Zachowanie w programie .NET 5,0 i nowszych wersjach:</span><span class="sxs-lookup"><span data-stu-id="2e13e-109">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a><span data-ttu-id="2e13e-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2e13e-110">Version introduced</span></span>

<span data-ttu-id="2e13e-111">5,0</span><span class="sxs-lookup"><span data-stu-id="2e13e-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2e13e-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="2e13e-112">Reason for change</span></span>

<span data-ttu-id="2e13e-113">Przekazywanie `null` dla `Type inputType` parametru jest nieakceptowalne i powinno zawsze generować <xref:System.ArgumentNullException> .</span><span class="sxs-lookup"><span data-stu-id="2e13e-113">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2e13e-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="2e13e-114">Recommended action</span></span>

<span data-ttu-id="2e13e-115">Upewnij się, że nie są przekazywane `null` `Type inputType` Parametry tych metod.</span><span class="sxs-lookup"><span data-stu-id="2e13e-115">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2e13e-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2e13e-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
