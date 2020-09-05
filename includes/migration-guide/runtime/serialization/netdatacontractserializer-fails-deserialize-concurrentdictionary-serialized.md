---
ms.openlocfilehash: 6c120f155660863ce5ae3cf5bd81ea858a68ef8d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496604"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a><span data-ttu-id="9b75b-101">NetDataContractSerializer nie może zdeserializować serializacji ConcurrentDictionary z inną wersją platformy .NET</span><span class="sxs-lookup"><span data-stu-id="9b75b-101">NetDataContractSerializer fails to deserialize a ConcurrentDictionary serialized with a different .NET version</span></span>

#### <a name="details"></a><span data-ttu-id="9b75b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="9b75b-102">Details</span></span>

<span data-ttu-id="9b75b-103">Zgodnie z projektem, <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> może być używany tylko wtedy, gdy obie operacje serializacji i deserializacji współużytkują te same typy CLR.</span><span class="sxs-lookup"><span data-stu-id="9b75b-103">By design, the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="9b75b-104">W związku z tym nie jest gwarantowane, że serializacja obiektu za pomocą jednej wersji .NET Framework może zostać odszeregowana przez inną wersję.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9b75b-104">Therefore, it is not guaranteed that an object serialized with one version of the .NET Framework can be deserialized by a different version.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span></span> <span data-ttu-id="9b75b-105">to typ, który jest znany jako nie do poprawnego deserializacji, jeśli jest serializowany z .NET Framework 4,5 lub wcześniejszym i deserializowany z .NET Framework 4.5.1 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="9b75b-105">is a type that is known to not to deserialize correctly if serialized with the .NET Framework 4.5 or earlier and deserialized with the .NET Framework 4.5.1 or later.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b75b-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="9b75b-106">Suggestion</span></span>

<span data-ttu-id="9b75b-107">Istnieje wiele możliwych obejścia tego problemu:</span><span class="sxs-lookup"><span data-stu-id="9b75b-107">There are a number of possible work-arounds for this issue:</span></span><ul><li><span data-ttu-id="9b75b-108">Uaktualnij komputer serializowany, aby używał również .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="9b75b-108">Upgrade the serializing computer to use the .NET Framework 4.5.1, as well.</span></span></li><li><span data-ttu-id="9b75b-109">Użyj <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> zamiast <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> tego, ponieważ nie oczekuje to dokładnie tych samych typów CLR zarówno w serializacji, jak i deserializacji zakończenia.</span><span class="sxs-lookup"><span data-stu-id="9b75b-109">Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> instead of <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> as this does not expect the exact same CLR types at both serializing and deserializing ends.</span></span></li><li><span data-ttu-id="9b75b-110">Użyj <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> zamiast <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> tego, ponieważ nie wykazuje tego konkretnego podziału 4,5- &gt; 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="9b75b-110">Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> instead of <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> since it does not exhibit this particular 4.5-&gt;4.5.1 break.</span></span></li></ul>

| <span data-ttu-id="9b75b-111">Nazwa</span><span class="sxs-lookup"><span data-stu-id="9b75b-111">Name</span></span>    | <span data-ttu-id="9b75b-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="9b75b-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b75b-113">Zakres</span><span class="sxs-lookup"><span data-stu-id="9b75b-113">Scope</span></span>   |<span data-ttu-id="9b75b-114">Mały</span><span class="sxs-lookup"><span data-stu-id="9b75b-114">Minor</span></span>|
|<span data-ttu-id="9b75b-115">Wersja</span><span class="sxs-lookup"><span data-stu-id="9b75b-115">Version</span></span>|<span data-ttu-id="9b75b-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="9b75b-116">4.5.1</span></span>|
|<span data-ttu-id="9b75b-117">Typ</span><span class="sxs-lookup"><span data-stu-id="9b75b-117">Type</span></span>|<span data-ttu-id="9b75b-118">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="9b75b-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9b75b-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9b75b-119">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)`

-->
