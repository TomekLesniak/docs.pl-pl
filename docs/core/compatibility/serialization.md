---
title: Zmiany dotyczące podziału serializacji
description: Wyświetla listę istotnych zmian w kategorii serializacji w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955342"
---
# <a name="serialization-breaking-changes"></a>Zmiany dotyczące podziału serializacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5,0 |
| [JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku](#jsonserializerdeserialize-requires-single-character-string) | 5,0 |
| [BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
