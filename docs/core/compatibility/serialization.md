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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="efc2e-103">Zmiany dotyczące podziału serializacji</span><span class="sxs-lookup"><span data-stu-id="efc2e-103">Serialization breaking changes</span></span>

<span data-ttu-id="efc2e-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="efc2e-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="efc2e-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="efc2e-105">Breaking change</span></span> | <span data-ttu-id="efc2e-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="efc2e-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="efc2e-107">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="efc2e-107">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="efc2e-108">5,0</span><span class="sxs-lookup"><span data-stu-id="efc2e-108">5.0</span></span> |
| [<span data-ttu-id="efc2e-109">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="efc2e-109">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="efc2e-110">5,0</span><span class="sxs-lookup"><span data-stu-id="efc2e-110">5.0</span></span> |
| [<span data-ttu-id="efc2e-111">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="efc2e-111">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="efc2e-112">5,0</span><span class="sxs-lookup"><span data-stu-id="efc2e-112">5.0</span></span> |
| [<span data-ttu-id="efc2e-113">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="efc2e-113">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="efc2e-114">5,0</span><span class="sxs-lookup"><span data-stu-id="efc2e-114">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="efc2e-115">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="efc2e-115">.NET 5.0</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
