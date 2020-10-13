---
ms.openlocfilehash: 572ebc47d26e30738fc4e5b8a8fab1f2643e3d83
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997730"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="95b5c-101">Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji</span><span class="sxs-lookup"><span data-stu-id="95b5c-101">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="95b5c-102">Aby zapewnić spójność wszystkich obsługiwanych monikerów platformy docelowej (TFMs), niepubliczne konstruktory bez parametrów nie są już używane do deserializacji z <xref:System.Text.Json.JsonSerializer> , domyślnie.</span><span class="sxs-lookup"><span data-stu-id="95b5c-102">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="95b5c-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="95b5c-103">Change description</span></span>

<span data-ttu-id="95b5c-104">W przypadku programu .NET Core 3,0 i 3,1 konstruktory wewnętrzne i prywatne mogą służyć do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="95b5c-104">On .NET Core 3.0 and 3.1, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="95b5c-105">W przypadku .NET Standard 2,0 i 2,1 konstruktory wewnętrzne i prywatne są niedozwolone i <xref:System.MissingMethodException> są generowane, jeśli nie jest zdefiniowany publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="95b5c-105">On .NET Standard 2.0 and 2.1, internal and private constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="95b5c-106">Począwszy od programu .NET 5,0, konstruktory niepubliczne, w tym konstruktory bez parametrów, są domyślnie ignorowane przez serializator.</span><span class="sxs-lookup"><span data-stu-id="95b5c-106">Starting in .NET 5.0, non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="95b5c-107">Serializator używa jednego z następujących konstruktorów do deserializacji:</span><span class="sxs-lookup"><span data-stu-id="95b5c-107">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="95b5c-108">Konstruktor publiczny z adnotacją <xref:System.Text.Json.Serialization.JsonConstructorAttribute> .</span><span class="sxs-lookup"><span data-stu-id="95b5c-108">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="95b5c-109">Publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="95b5c-109">Public parameterless constructor.</span></span>
- <span data-ttu-id="95b5c-110">Publiczny Konstruktor sparametryzowany (jeśli jest to jedyny Konstruktor publiczny obecny).</span><span class="sxs-lookup"><span data-stu-id="95b5c-110">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="95b5c-111">Jeśli żaden z tych konstruktorów nie jest dostępny, <xref:System.NotSupportedException> jest zgłaszany w przypadku próby deserializacji typu.</span><span class="sxs-lookup"><span data-stu-id="95b5c-111">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95b5c-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="95b5c-112">Version introduced</span></span>

<span data-ttu-id="95b5c-113">5,0</span><span class="sxs-lookup"><span data-stu-id="95b5c-113">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="95b5c-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="95b5c-114">Reason for change</span></span>

- <span data-ttu-id="95b5c-115">Aby wymusić spójne zachowanie między wszystkimi monikerami platformy docelowej (TFMs), które <xref:System.Text.Json?displayProperty=fullName> kompilują program (.NET Core 3,0 i nowsze wersje oraz .NET Standard 2,0 i 2,1)</span><span class="sxs-lookup"><span data-stu-id="95b5c-115">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions, and .NET Standard 2.0 and 2.1)</span></span>
- <span data-ttu-id="95b5c-116">Ponieważ <xref:System.Text.Json.JsonSerializer> nie należy wywoływać obszaru powierzchni niepublicznej typu, niezależnie od tego, czy jest to Konstruktor, właściwość, czy pole.</span><span class="sxs-lookup"><span data-stu-id="95b5c-116">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95b5c-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="95b5c-117">Recommended action</span></span>

- <span data-ttu-id="95b5c-118">Jeśli jesteś własnością typu i jest to możliwe, ustaw konstruktora bez parametrów jako publiczny.</span><span class="sxs-lookup"><span data-stu-id="95b5c-118">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="95b5c-119">W przeciwnym razie należy zaimplementować `JsonConverter<T>` dla typu i kontrolować zachowanie deserializacji.</span><span class="sxs-lookup"><span data-stu-id="95b5c-119">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="95b5c-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="95b5c-120">Category</span></span>

<span data-ttu-id="95b5c-121">Serializacja</span><span class="sxs-lookup"><span data-stu-id="95b5c-121">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95b5c-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="95b5c-122">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
