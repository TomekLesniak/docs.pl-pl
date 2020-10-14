---
title: Zmiany dotyczące podziału serializacji
description: Wyświetla listę istotnych zmian w kategorii serializacji w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 07/30/2020
ms.openlocfilehash: bb6bd650afeba426edc6e102076f05f97f8e0598
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050477"
---
# <a name="serialization-breaking-changes"></a>Zmiany dotyczące podziału serializacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | 5,0 |
| [Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji](#non-public-parameterless-constructors-not-used-for-deserialization) | 5,0 |
| [JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5,0 |
| [JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku](#jsonserializerdeserialize-requires-single-character-string) | 5,0 |
| [BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

***

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
