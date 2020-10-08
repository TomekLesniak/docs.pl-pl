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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="14d9c-103">Zmiany dotyczące podziału serializacji</span><span class="sxs-lookup"><span data-stu-id="14d9c-103">Serialization breaking changes</span></span>

<span data-ttu-id="14d9c-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="14d9c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="14d9c-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="14d9c-105">Breaking change</span></span> | <span data-ttu-id="14d9c-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="14d9c-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="14d9c-107">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="14d9c-107">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="14d9c-108">5,0</span><span class="sxs-lookup"><span data-stu-id="14d9c-108">5.0</span></span> |
| [<span data-ttu-id="14d9c-109">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="14d9c-109">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="14d9c-110">5,0</span><span class="sxs-lookup"><span data-stu-id="14d9c-110">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="14d9c-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="14d9c-111">.NET 5.0</span></span>

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
