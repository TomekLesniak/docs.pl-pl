---
title: 'Zmiana dotycząca podziału: niepublicznych konstruktorów bez parametrów, które nie są używane do deserializacji'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, w której niepubliczne konstruktory bez parametrów nie są już używane do deserializacji z JsonSerializer.
ms.date: 10/18/2020
ms.openlocfilehash: 6bdcc92c61008aa4ee27370bbac4dbf4ee3ef7c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761648"
---
# <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="75563-103">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="75563-103">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="75563-104">Aby zapewnić spójność wszystkich obsługiwanych monikerów platformy docelowej (TFMs), niepubliczne konstruktory bez parametrów nie są już używane do deserializacji z <xref:System.Text.Json.JsonSerializer> , domyślnie.</span><span class="sxs-lookup"><span data-stu-id="75563-104">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

## <a name="change-description"></a><span data-ttu-id="75563-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="75563-105">Change description</span></span>

<span data-ttu-id="75563-106">Autonomiczna [System.Text.Jsw pakietach NuGet](https://www.nuget.org/packages/System.Text.Json/) obsługujących .NET Standard 2,0 i wyższych, czyli wersje 4.6.0-4.7.2, zachowują się spójnie z wbudowanym zachowaniem programu .net Core 3,0 i 3,1.</span><span class="sxs-lookup"><span data-stu-id="75563-106">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="75563-107">W przypadku programu .NET Core 3. x konstruktory wewnętrzne i prywatne mogą służyć do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="75563-107">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="75563-108">W pakietach autonomicznych konstruktory niepubliczne są niedozwolone i <xref:System.MissingMethodException> są generowane, jeśli nie jest zdefiniowany publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="75563-108">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="75563-109">Począwszy od platformy .NET 5,0 i System.Text.Jsw pakiecie NuGet 5.0.0, zachowanie jest spójne między pakietem NuGet a wbudowanymi interfejsami API.</span><span class="sxs-lookup"><span data-stu-id="75563-109">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="75563-110">Konstruktory niepubliczne, w tym konstruktory bez parametrów, są domyślnie ignorowane przez serializator.</span><span class="sxs-lookup"><span data-stu-id="75563-110">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="75563-111">Serializator używa jednego z następujących konstruktorów do deserializacji:</span><span class="sxs-lookup"><span data-stu-id="75563-111">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="75563-112">Konstruktor publiczny z adnotacją <xref:System.Text.Json.Serialization.JsonConstructorAttribute> .</span><span class="sxs-lookup"><span data-stu-id="75563-112">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="75563-113">Publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="75563-113">Public parameterless constructor.</span></span>
- <span data-ttu-id="75563-114">Publiczny Konstruktor sparametryzowany (jeśli jest to jedyny Konstruktor publiczny obecny).</span><span class="sxs-lookup"><span data-stu-id="75563-114">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="75563-115">Jeśli żaden z tych konstruktorów nie jest dostępny, <xref:System.NotSupportedException> jest zgłaszany w przypadku próby deserializacji typu.</span><span class="sxs-lookup"><span data-stu-id="75563-115">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="75563-116">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="75563-116">Version introduced</span></span>

<span data-ttu-id="75563-117">5,0</span><span class="sxs-lookup"><span data-stu-id="75563-117">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="75563-118">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="75563-118">Reason for change</span></span>

- <span data-ttu-id="75563-119">Aby wymusić spójne zachowanie między wszystkimi monikerami platformy docelowej (TFMs), które <xref:System.Text.Json?displayProperty=fullName> kompilują program (.NET Core 3,0 i nowsze wersje i .NET Standard 2,0)</span><span class="sxs-lookup"><span data-stu-id="75563-119">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="75563-120">Ponieważ <xref:System.Text.Json.JsonSerializer> nie należy wywoływać obszaru powierzchni niepublicznej typu, niezależnie od tego, czy jest to Konstruktor, właściwość, czy pole.</span><span class="sxs-lookup"><span data-stu-id="75563-120">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="75563-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="75563-121">Recommended action</span></span>

- <span data-ttu-id="75563-122">Jeśli jesteś własnością typu i jest to możliwe, ustaw konstruktora bez parametrów jako publiczny.</span><span class="sxs-lookup"><span data-stu-id="75563-122">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="75563-123">W przeciwnym razie należy zaimplementować `JsonConverter<T>` dla typu i kontrolować zachowanie deserializacji.</span><span class="sxs-lookup"><span data-stu-id="75563-123">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="75563-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="75563-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
