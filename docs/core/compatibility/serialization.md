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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="4d314-103">Zmiany dotyczące podziału serializacji</span><span class="sxs-lookup"><span data-stu-id="4d314-103">Serialization breaking changes</span></span>

<span data-ttu-id="4d314-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="4d314-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4d314-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="4d314-105">Breaking change</span></span> | <span data-ttu-id="4d314-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="4d314-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="4d314-107">Aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów</span><span class="sxs-lookup"><span data-stu-id="4d314-107">ASP.NET Core apps allow deserializing quoted numbers</span></span>](#aspnet-core-apps-allow-deserializing-quoted-numbers) | <span data-ttu-id="4d314-108">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-108">5.0</span></span> |
| [<span data-ttu-id="4d314-109">Opcje PropertyNamingPolicy, PropertyNameCaseInsensitive i Encoder są honorowane podczas serializacji i deserializacji par klucz-wartość</span><span class="sxs-lookup"><span data-stu-id="4d314-109">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="4d314-110">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-110">5.0</span></span> |
| [<span data-ttu-id="4d314-111">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="4d314-111">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="4d314-112">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-112">5.0</span></span> |
| [<span data-ttu-id="4d314-113">JsonSerializer. serializować zwraca ArgumentNullException, gdy parametr typu ma wartość null</span><span class="sxs-lookup"><span data-stu-id="4d314-113">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="4d314-114">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-114">5.0</span></span> |
| [<span data-ttu-id="4d314-115">JsonSerializer. deserializacji wymaga ciągu pojedynczego znaku</span><span class="sxs-lookup"><span data-stu-id="4d314-115">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="4d314-116">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-116">5.0</span></span> |
| [<span data-ttu-id="4d314-117">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="4d314-117">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="4d314-118">5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-118">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="4d314-119">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="4d314-119">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

<span data-ttu-id="4d314-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="4d314-120">\*\*_</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

<span data-ttu-id="4d314-121">_\*\*</span><span class="sxs-lookup"><span data-stu-id="4d314-121">_\*\*</span></span>
