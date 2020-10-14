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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="a0b9e-103">Zmiany dotyczące podziału serializacji</span><span class="sxs-lookup"><span data-stu-id="a0b9e-103">Serialization breaking changes</span></span>

<span data-ttu-id="a0b9e-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="a0b9e-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a0b9e-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="a0b9e-105">Breaking change</span></span> | <span data-ttu-id="a0b9e-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a0b9e-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="a0b9e-107">Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość</span><span class="sxs-lookup"><span data-stu-id="a0b9e-107">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="a0b9e-108">5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-108">5.0</span></span> |
| [<span data-ttu-id="a0b9e-109">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="a0b9e-109">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="a0b9e-110">5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-110">5.0</span></span> |
| [<span data-ttu-id="a0b9e-111">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="a0b9e-111">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="a0b9e-112">5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-112">5.0</span></span> |
| [<span data-ttu-id="a0b9e-113">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="a0b9e-113">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="a0b9e-114">5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-114">5.0</span></span> |
| [<span data-ttu-id="a0b9e-115">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="a0b9e-115">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="a0b9e-116">5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-116">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="a0b9e-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a0b9e-117">.NET 5.0</span></span>

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
