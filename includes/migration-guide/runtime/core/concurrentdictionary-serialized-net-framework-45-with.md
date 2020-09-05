---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497557"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a><span data-ttu-id="57c1c-101">Serializacja ConcurrentDictionary w .NET Framework 4,5 z NetDataContractSerializerem nie może zostać zdeserializować przez .NET Framework 4.5.1 lub 4.5.2</span><span class="sxs-lookup"><span data-stu-id="57c1c-101">A ConcurrentDictionary serialized in .NET Framework 4.5 with NetDataContractSerializer cannot be deserialized by .NET Framework 4.5.1 or 4.5.2</span></span>

#### <a name="details"></a><span data-ttu-id="57c1c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="57c1c-102">Details</span></span>

<span data-ttu-id="57c1c-103">Ze względu na wewnętrzne zmiany typu <xref:System.Collections.Concurrent.ConcurrentDictionary%602> obiekty, które są serializowane z .NET Framework 4,5 przy użyciu <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> nie można deserializować w .NET Framework 4.5.1 lub w .NET Framework 4.5.2. Zauważ, że poruszane w innym kierunku (Serializacja przy użyciu .NET Framework 4.5. x i deserializacji z .NET Framework 4,5).</span><span class="sxs-lookup"><span data-stu-id="57c1c-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="57c1c-104">Podobnie, wszystkie 4. x serializacji między wersjami współdziałają z .NET Framework 4.6. Serializacja i deserializacja z jedną wersją .NET Framework nie ma żadnego oddziaływania.</span><span class="sxs-lookup"><span data-stu-id="57c1c-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="57c1c-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="57c1c-105">Suggestion</span></span>

<span data-ttu-id="57c1c-106">Jeśli konieczne jest Serializacja i deserializacja <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> między .NET Framework 4,5 i .NET Framework 4.5.1/4.5.2, <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> zamiast elementu należy użyć alternatywnego serializatora, takiego jak serializator lub <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> . Alternatywnie, ponieważ ten problem został rozwiązany w .NET Framework 4,6, może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57c1c-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="57c1c-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="57c1c-107">Name</span></span>    | <span data-ttu-id="57c1c-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="57c1c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="57c1c-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="57c1c-109">Scope</span></span>   |<span data-ttu-id="57c1c-110">Mały</span><span class="sxs-lookup"><span data-stu-id="57c1c-110">Minor</span></span>|
|<span data-ttu-id="57c1c-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="57c1c-111">Version</span></span>|<span data-ttu-id="57c1c-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="57c1c-112">4.5.1</span></span>|
|<span data-ttu-id="57c1c-113">Typ</span><span class="sxs-lookup"><span data-stu-id="57c1c-113">Type</span></span>|<span data-ttu-id="57c1c-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="57c1c-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="57c1c-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="57c1c-115">Affected APIs</span></span>

<span data-ttu-id="57c1c-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="57c1c-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
