---
title: Zmiany dotyczące podziału serializacji
description: Wyświetla listę istotnych zmian w kategorii serializacji w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 07/30/2020
ms.openlocfilehash: d68bb95f4ee2b21a5a5bf002a46a3904543cd4a7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844511"
---
# <a name="serialization-breaking-changes"></a>Zmiany dotyczące podziału serializacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku](#jsonserializerdeserialize-requires-single-character-string) | 5,0 |
| [BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
