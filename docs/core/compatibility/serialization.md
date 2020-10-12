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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="f8f15-103">Zmiany dotyczące podziału serializacji</span><span class="sxs-lookup"><span data-stu-id="f8f15-103">Serialization breaking changes</span></span>

<span data-ttu-id="f8f15-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="f8f15-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="f8f15-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="f8f15-105">Breaking change</span></span> | <span data-ttu-id="f8f15-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f8f15-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="f8f15-107">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="f8f15-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="f8f15-108">5,0</span><span class="sxs-lookup"><span data-stu-id="f8f15-108">5.0</span></span> |
| [<span data-ttu-id="f8f15-109">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="f8f15-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="f8f15-110">5,0</span><span class="sxs-lookup"><span data-stu-id="f8f15-110">5.0</span></span> |
| [<span data-ttu-id="f8f15-111">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="f8f15-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="f8f15-112">5,0</span><span class="sxs-lookup"><span data-stu-id="f8f15-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="f8f15-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="f8f15-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
