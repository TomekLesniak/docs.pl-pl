---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050476"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a>Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość

<xref:System.Text.Json.JsonSerializer> teraz w <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.Encoder> trakcie serializacji <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> nazw właściwości i wystąpienia są uwzględniane opcje i <xref:System.Collections.Generic.KeyValuePair%602> . Ponadto program uwzględnia <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opcje i podczas deserializacji <xref:System.Collections.Generic.KeyValuePair%602> wystąpień.

#### <a name="change-description"></a>Zmień opis

##### <a name="serialization"></a>Serializacja

W wersjach programu .NET Core 3. x i wSystem.Text.Jswersjach 4.6.0-4.7.2 w [ pakiecie NuGet](https://www.nuget.org/packages/System.Text.Json)właściwości <xref:System.Collections.Generic.KeyValuePair%602> wystąpień są zawsze serializowane tylko jako "klucz" i "wartość", niezależnie od <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> opcji i. Poniższy przykład kodu pokazuje, w jaki <xref:System.Collections.Generic.KeyValuePair%602.Key> sposób <xref:System.Collections.Generic.KeyValuePair%602.Value> właściwości i *nie* są notacji CamelCase — wielkość liter po serializacji, mimo że określone zasady nazewnictwa właściwości wymuszają takie działanie.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

Począwszy od platformy .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.Encoder> Opcje i są honorowane podczas serializacji <xref:System.Collections.Generic.KeyValuePair%602> wystąpień. Poniższy przykład kodu pokazuje, jak <xref:System.Collections.Generic.KeyValuePair%602.Key> właściwości i <xref:System.Collections.Generic.KeyValuePair%602.Value> są notacji CamelCase — wielkość liter po serializacji, zgodnie z określonymi zasadami nazewnictwa właściwości.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a>Deserializacji

W wersjach programu .NET Core 3. x i w wersjach 4.7. x [System.Text.Jsw pakiecie NuGet](https://www.nuget.org/packages/System.Text.Json), <xref:System.Text.Json.JsonException> jest generowany, gdy nazwy właściwości JSON nie są dokładne `Key` i `Value` , na przykład, jeśli nie zaczynają się wielką literą. Wyjątek jest zgłaszany, nawet jeśli określone zasady nazewnictwa właściwości wyraźnie zezwala na to.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

Począwszy od platformy .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opcje i są honorowane podczas deserializacji przy użyciu <xref:System.Text.Json.JsonSerializer> . Na przykład poniższy fragment kodu przedstawia pomyślne deserializacja małych liter <xref:System.Collections.Generic.KeyValuePair%602.Key> i <xref:System.Collections.Generic.KeyValuePair%602.Value> nazw właściwości, ponieważ zezwala na to określone zasady nazewnictwa właściwości.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

Aby obsłużyć ładunki, które były serializowane z poprzednimi wersjami, "klucz" i "wartość" są specjalną wielkością liter do dopasowania podczas deserializacji. Mimo że <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> nazwy właściwości i nie są notacji CamelCase w przypadku uwzględnienia w <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> opcji w poniższym przykładzie kodu, deserializacji powiodło się.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="reason-for-change"></a>Przyczyna zmiany

Istotne Opinie klientów wskazują, że <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> powinny być honorowane. W celu <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> zapewnienia kompletności opcji i <xref:System.Text.Json.JsonSerializerOptions.Encoder> są również honorowane, tak że <xref:System.Collections.Generic.KeyValuePair%602> wystąpienia są traktowane tak samo jak każdy inny zwykły obiekt CLR (POCO).

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli ta zmiana będzie zakłócać pracę, możesz użyć [niestandardowego konwertera](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) , który implementuje pożądaną semantykę.

#### <a name="category"></a>Kategoria

Serializacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
