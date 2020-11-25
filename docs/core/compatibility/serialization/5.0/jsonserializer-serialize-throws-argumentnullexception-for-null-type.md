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
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null

<xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> , i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> przeciążenia, które mają parametr typu, <xref:System.Type> są teraz zgłaszane <xref:System.ArgumentNullException> za każdym razem, gdy `null` zostanie przesłany dla tego parametru.

## <a name="change-description"></a>Zmień opis

W przypadku programu .NET Core 3,1,, <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> i <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads, które mają <xref:System.Type> parametr throw <xref:System.ArgumentNullException> gdy `null` jest przenoszona do `Type inputType` parametru, ale nie w przypadku, gdy `Object value` parametr jest również `null` . Począwszy od platformy .NET 5,0, metody te *zawsze* generują <xref:System.ArgumentNullException> gdy `null` jest przenoszona dla <xref:System.Type> parametru.

Zachowanie w programie .NET Core 3,1:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

Zachowanie w programie .NET 5,0 i nowszych wersjach:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="reason-for-change"></a>Przyczyna zmiany

Przekazywanie `null` dla `Type inputType` parametru jest nieakceptowalne i powinno zawsze generować <xref:System.ArgumentNullException> .

## <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że nie są przekazywane `null` `Type inputType` Parametry tych metod.

## <a name="affected-apis"></a>Dotyczy interfejsów API

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
