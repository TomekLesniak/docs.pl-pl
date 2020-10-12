---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955343"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="d8bf2-101">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="d8bf2-101">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="d8bf2-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> , i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> przeciążenia, które mają parametr, są teraz zgłaszane za <xref:System.Type> <xref:System.ArgumentNullException> każdym razem, gdy `null` zostanie przesłany <xref:System.Type> parametr.</span><span class="sxs-lookup"><span data-stu-id="d8bf2-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter now throw an <xref:System.ArgumentNullException> whenever `null` is passed for the <xref:System.Type> parameter.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d8bf2-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d8bf2-103">Change description</span></span>

<span data-ttu-id="d8bf2-104">W przypadku programu .NET Core 3,1,, <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads, które mają <xref:System.Type> parametr throw <xref:System.ArgumentNullException> gdy `null` jest przenoszona do `Type inputType` parametru, ale nie w przypadku, gdy `Object value` parametr jest również `null` .</span><span class="sxs-lookup"><span data-stu-id="d8bf2-104">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="d8bf2-105">Począwszy od platformy .NET 5,0, metody te *zawsze* generują <xref:System.ArgumentNullException> gdy `null` jest przenoszona dla <xref:System.Type> parametru.</span><span class="sxs-lookup"><span data-stu-id="d8bf2-105">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="d8bf2-106">Zachowanie w programie .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="d8bf2-106">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="d8bf2-107">Zachowanie w programie .NET 5,0 i nowszych wersjach:</span><span class="sxs-lookup"><span data-stu-id="d8bf2-107">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a><span data-ttu-id="d8bf2-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d8bf2-108">Version introduced</span></span>

<span data-ttu-id="d8bf2-109">5,0</span><span class="sxs-lookup"><span data-stu-id="d8bf2-109">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d8bf2-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d8bf2-110">Reason for change</span></span>

<span data-ttu-id="d8bf2-111">Przekazywanie `null` dla `Type inputType` parametru jest nieakceptowalne i powinno zawsze generować <xref:System.ArgumentNullException> .</span><span class="sxs-lookup"><span data-stu-id="d8bf2-111">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d8bf2-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d8bf2-112">Recommended action</span></span>

<span data-ttu-id="d8bf2-113">Upewnij się, że nie są przekazywane `null` `Type inputType` Parametry tych metod.</span><span class="sxs-lookup"><span data-stu-id="d8bf2-113">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="d8bf2-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d8bf2-114">Category</span></span>

<span data-ttu-id="d8bf2-115">Serializacja</span><span class="sxs-lookup"><span data-stu-id="d8bf2-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d8bf2-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d8bf2-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
