---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496755"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="d0f8a-101">SoapFormatter nie może rozszeregować obiektów Hashtable i podobnej kolejności kolekcji</span><span class="sxs-lookup"><span data-stu-id="d0f8a-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="d0f8a-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d0f8a-102">Details</span></span>

<span data-ttu-id="d0f8a-103">Program nie <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> gwarantuje, że Serializacja obiektów w jednej wersji .NET Framework zostanie pomyślnie rozszeregowana w ramach innej wersji.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="d0f8a-104">W przypadku niektórych uporządkowanych kolekcji (takich jak <xref:System.Collections.Hashtable?displayProperty=fullName> ) dodano członków między 4,0 i 4,5 takich, że obiekty tych typów nie mogą deserializować z .NET Framework 4,0, jeśli zostały zserializowane z .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="d0f8a-105">Należy pamiętać, że jeśli serializowane dane są serializowane i deserializowane z tą samą wersją .NET Framework, żaden problem nie wystąpi.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d0f8a-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d0f8a-106">Suggestion</span></span>

<span data-ttu-id="d0f8a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> Serializacja powinna zostać zastąpiona <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializacją lub <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> być odporna na zmiany .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="d0f8a-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d0f8a-108">Name</span></span>    | <span data-ttu-id="d0f8a-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="d0f8a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d0f8a-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="d0f8a-110">Scope</span></span>   |<span data-ttu-id="d0f8a-111">Mały</span><span class="sxs-lookup"><span data-stu-id="d0f8a-111">Minor</span></span>|
|<span data-ttu-id="d0f8a-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="d0f8a-112">Version</span></span>|<span data-ttu-id="d0f8a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d0f8a-113">4.5</span></span>|
|<span data-ttu-id="d0f8a-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d0f8a-114">Type</span></span>|<span data-ttu-id="d0f8a-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d0f8a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d0f8a-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d0f8a-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
