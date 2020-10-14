---
ms.openlocfilehash: 3692848a0cbd4bbbe3c7bb4d2c22a2b19de732e4
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050478"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="1dc37-101">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="1dc37-101">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="1dc37-102">Aby zapewnić spójność wszystkich obsługiwanych monikerów platformy docelowej (TFMs), niepubliczne konstruktory bez parametrów nie są już używane do deserializacji z <xref:System.Text.Json.JsonSerializer> , domyślnie.</span><span class="sxs-lookup"><span data-stu-id="1dc37-102">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1dc37-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="1dc37-103">Change description</span></span>

<span data-ttu-id="1dc37-104">Autonomiczna [System.Text.Jsw pakietach NuGet](https://www.nuget.org/packages/System.Text.Json/) obsługujących .NET Standard 2,0 i wyższych, czyli wersje 4.6.0-4.7.2, zachowują się spójnie z wbudowanym zachowaniem programu .net Core 3,0 i 3,1.</span><span class="sxs-lookup"><span data-stu-id="1dc37-104">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="1dc37-105">W przypadku programu .NET Core 3. x konstruktory wewnętrzne i prywatne mogą służyć do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="1dc37-105">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="1dc37-106">W pakietach autonomicznych konstruktory niepubliczne są niedozwolone i <xref:System.MissingMethodException> są generowane, jeśli nie jest zdefiniowany publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="1dc37-106">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="1dc37-107">Począwszy od platformy .NET 5,0 i System.Text.Jsw pakiecie NuGet 5.0.0, zachowanie jest spójne między pakietem NuGet a wbudowanymi interfejsami API.</span><span class="sxs-lookup"><span data-stu-id="1dc37-107">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="1dc37-108">Konstruktory niepubliczne, w tym konstruktory bez parametrów, są domyślnie ignorowane przez serializator.</span><span class="sxs-lookup"><span data-stu-id="1dc37-108">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="1dc37-109">Serializator używa jednego z następujących konstruktorów do deserializacji:</span><span class="sxs-lookup"><span data-stu-id="1dc37-109">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="1dc37-110">Konstruktor publiczny z adnotacją <xref:System.Text.Json.Serialization.JsonConstructorAttribute> .</span><span class="sxs-lookup"><span data-stu-id="1dc37-110">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="1dc37-111">Publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="1dc37-111">Public parameterless constructor.</span></span>
- <span data-ttu-id="1dc37-112">Publiczny Konstruktor sparametryzowany (jeśli jest to jedyny Konstruktor publiczny obecny).</span><span class="sxs-lookup"><span data-stu-id="1dc37-112">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="1dc37-113">Jeśli żaden z tych konstruktorów nie jest dostępny, <xref:System.NotSupportedException> jest zgłaszany w przypadku próby deserializacji typu.</span><span class="sxs-lookup"><span data-stu-id="1dc37-113">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1dc37-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="1dc37-114">Version introduced</span></span>

<span data-ttu-id="1dc37-115">5,0</span><span class="sxs-lookup"><span data-stu-id="1dc37-115">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1dc37-116">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="1dc37-116">Reason for change</span></span>

- <span data-ttu-id="1dc37-117">Aby wymusić spójne zachowanie między wszystkimi monikerami platformy docelowej (TFMs), które <xref:System.Text.Json?displayProperty=fullName> kompilują program (.NET Core 3,0 i nowsze wersje i .NET Standard 2,0)</span><span class="sxs-lookup"><span data-stu-id="1dc37-117">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="1dc37-118">Ponieważ <xref:System.Text.Json.JsonSerializer> nie należy wywoływać obszaru powierzchni niepublicznej typu, niezależnie od tego, czy jest to Konstruktor, właściwość, czy pole.</span><span class="sxs-lookup"><span data-stu-id="1dc37-118">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1dc37-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="1dc37-119">Recommended action</span></span>

- <span data-ttu-id="1dc37-120">Jeśli jesteś własnością typu i jest to możliwe, ustaw konstruktora bez parametrów jako publiczny.</span><span class="sxs-lookup"><span data-stu-id="1dc37-120">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="1dc37-121">W przeciwnym razie należy zaimplementować `JsonConverter<T>` dla typu i kontrolować zachowanie deserializacji.</span><span class="sxs-lookup"><span data-stu-id="1dc37-121">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="1dc37-122">Kategoria</span><span class="sxs-lookup"><span data-stu-id="1dc37-122">Category</span></span>

<span data-ttu-id="1dc37-123">Serializacja</span><span class="sxs-lookup"><span data-stu-id="1dc37-123">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1dc37-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1dc37-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
