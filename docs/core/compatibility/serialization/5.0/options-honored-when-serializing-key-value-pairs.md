---
title: 'Nieprzerwana zmiana: opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane dla par klucz-wartość'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0, w której opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji nazw właściwości klucza i wartości wystąpienia pary klucz-wartość.
ms.date: 10/18/2020
ms.openlocfilehash: 5d75cb7feea32cc4b942e5261c5b609e00a5082c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761632"
---
# <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="5cba1-103">Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość</span><span class="sxs-lookup"><span data-stu-id="5cba1-103">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="5cba1-104"><xref:System.Text.Json.JsonSerializer> teraz w <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.Encoder> trakcie serializacji <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> nazw właściwości i wystąpienia są uwzględniane opcje i <xref:System.Collections.Generic.KeyValuePair%602> .</span><span class="sxs-lookup"><span data-stu-id="5cba1-104"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="5cba1-105">Ponadto program uwzględnia <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opcje i podczas deserializacji <xref:System.Collections.Generic.KeyValuePair%602> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="5cba1-105">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

## <a name="change-description"></a><span data-ttu-id="5cba1-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="5cba1-106">Change description</span></span>

### <a name="serialization"></a><span data-ttu-id="5cba1-107">Serializacja</span><span class="sxs-lookup"><span data-stu-id="5cba1-107">Serialization</span></span>

<span data-ttu-id="5cba1-108">W wersjach programu .NET Core 3. x i wSystem.Text.Jswersjach 4.6.0-4.7.2 w [ pakiecie NuGet](https://www.nuget.org/packages/System.Text.Json)właściwości <xref:System.Collections.Generic.KeyValuePair%602> wystąpień są zawsze serializowane tylko jako "klucz" i "wartość", niezależnie od <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> opcji i.</span><span class="sxs-lookup"><span data-stu-id="5cba1-108">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="5cba1-109">Poniższy przykład kodu pokazuje, w jaki <xref:System.Collections.Generic.KeyValuePair%602.Key> sposób <xref:System.Collections.Generic.KeyValuePair%602.Value> właściwości i *nie* są notacji CamelCase — wielkość liter po serializacji, mimo że określone zasady nazewnictwa właściwości wymuszają takie działanie.</span><span class="sxs-lookup"><span data-stu-id="5cba1-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="5cba1-110">Począwszy od platformy .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.Encoder> Opcje i są honorowane podczas serializacji <xref:System.Collections.Generic.KeyValuePair%602> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="5cba1-110">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="5cba1-111">Poniższy przykład kodu pokazuje, jak <xref:System.Collections.Generic.KeyValuePair%602.Key> właściwości i <xref:System.Collections.Generic.KeyValuePair%602.Value> są notacji CamelCase — wielkość liter po serializacji, zgodnie z określonymi zasadami nazewnictwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="5cba1-111">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

### <a name="deserialization"></a><span data-ttu-id="5cba1-112">Deserializacji</span><span class="sxs-lookup"><span data-stu-id="5cba1-112">Deserialization</span></span>

<span data-ttu-id="5cba1-113">W wersjach programu .NET Core 3. x i w wersjach 4.7. x [System.Text.Jsw pakiecie NuGet](https://www.nuget.org/packages/System.Text.Json), <xref:System.Text.Json.JsonException> jest generowany, gdy nazwy właściwości JSON nie są dokładne `Key` i `Value` , na przykład, jeśli nie zaczynają się wielką literą.</span><span class="sxs-lookup"><span data-stu-id="5cba1-113">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="5cba1-114">Wyjątek jest zgłaszany, nawet jeśli określone zasady nazewnictwa właściwości wyraźnie zezwala na to.</span><span class="sxs-lookup"><span data-stu-id="5cba1-114">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="5cba1-115">Począwszy od platformy .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opcje i są honorowane podczas deserializacji przy użyciu <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="5cba1-115">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="5cba1-116">Na przykład poniższy fragment kodu przedstawia pomyślne deserializacja małych liter <xref:System.Collections.Generic.KeyValuePair%602.Key> i <xref:System.Collections.Generic.KeyValuePair%602.Value> nazw właściwości, ponieważ zezwala na to określone zasady nazewnictwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="5cba1-116">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="5cba1-117">Aby obsłużyć ładunki, które były serializowane z poprzednimi wersjami, "klucz" i "wartość" są specjalną wielkością liter do dopasowania podczas deserializacji.</span><span class="sxs-lookup"><span data-stu-id="5cba1-117">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="5cba1-118">Mimo że <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> nazwy właściwości i nie są notacji CamelCase w przypadku uwzględnienia w <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> opcji w poniższym przykładzie kodu, deserializacji powiodło się.</span><span class="sxs-lookup"><span data-stu-id="5cba1-118">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

## <a name="version-introduced"></a><span data-ttu-id="5cba1-119">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="5cba1-119">Version introduced</span></span>

<span data-ttu-id="5cba1-120">5,0</span><span class="sxs-lookup"><span data-stu-id="5cba1-120">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5cba1-121">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="5cba1-121">Reason for change</span></span>

<span data-ttu-id="5cba1-122">Istotne Opinie klientów wskazują, że <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> powinny być honorowane.</span><span class="sxs-lookup"><span data-stu-id="5cba1-122">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="5cba1-123">W celu <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> zapewnienia kompletności opcji i <xref:System.Text.Json.JsonSerializerOptions.Encoder> są również honorowane, tak że <xref:System.Collections.Generic.KeyValuePair%602> wystąpienia są traktowane tak samo jak każdy inny zwykły obiekt CLR (POCO).</span><span class="sxs-lookup"><span data-stu-id="5cba1-123">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5cba1-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="5cba1-124">Recommended action</span></span>

<span data-ttu-id="5cba1-125">Jeśli ta zmiana będzie zakłócać pracę, możesz użyć [niestandardowego konwertera](../../../../standard/serialization/system-text-json-converters-how-to.md) , który implementuje pożądaną semantykę.</span><span class="sxs-lookup"><span data-stu-id="5cba1-125">If this change is disruptive to you, you can use a [custom converter](../../../../standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5cba1-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5cba1-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
