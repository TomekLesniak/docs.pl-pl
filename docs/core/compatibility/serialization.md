---
title: Zmiany dotyczące podziału serializacji
description: Wyświetla listę istotnych zmian w kategorii serializacji w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 07/30/2020
ms.openlocfilehash: 67608c8e7a9745c060b7eb179fe5a956ede9f80f
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332886"
---
# <a name="serialization-breaking-changes"></a>Zmiany dotyczące podziału serializacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [Aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów](#aspnet-core-apps-allow-deserializing-quoted-numbers) | 5,0 |
| [Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | 5,0 |
| [Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji](#non-public-parameterless-constructors-not-used-for-deserialization) | 5,0 |
| [JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5,0 |
| [JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku](#jsonserializerdeserialize-requires-single-character-string) | 5,0 |
| [BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

**_

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

_**
