---
title: Zmiany dotyczące podziału serializacji
description: Wyświetla listę istotnych zmian w kategorii serializacji w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 07/30/2020
ms.openlocfilehash: 6902ef8eb2dc23610ef532ff57b755456648ffb0
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997707"
---
# <a name="serialization-breaking-changes"></a>Zmiany dotyczące podziału serializacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji](#non-public-parameterless-constructors-not-used-for-deserialization) | 5,0 |
| [JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5,0 |
| [JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku](#jsonserializerdeserialize-requires-single-character-string) | 5,0 |
| [BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
