---
ms.openlocfilehash: 75c7385bceec2595683d1c0d97a7df9264e3bf0b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497382"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="f86d4-101">Operacja XmlSerializer kończy się niepowodzeniem podczas serializacji typu, który ukrywa dostępną składową z niedostępnym jednym</span><span class="sxs-lookup"><span data-stu-id="f86d4-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

#### <a name="details"></a><span data-ttu-id="f86d4-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f86d4-102">Details</span></span>

<span data-ttu-id="f86d4-103">Podczas serializacji typu pochodnego <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> może się nie powieść, jeśli typ zawiera niedostępne pole lub właściwość, która ukrywa (za pomocą słowa kluczowego "New") pole lub właściwość o tej samej nazwie, która była wcześniej dostępna (na przykład jako publiczna) w typie podstawowym.</span><span class="sxs-lookup"><span data-stu-id="f86d4-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f86d4-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f86d4-104">Suggestion</span></span>

<span data-ttu-id="f86d4-105">Ten problem można rozwiązać, tworząc nowy, ukrywając element członkowski dostępny dla (na <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> przykład poprzez oznaczenie go jako publiczny). Alternatywnie następujące ustawienie konfiguracji spowoduje przywrócenie <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> zachowania 4,0, co spowoduje rozwiązanie problemu:</span><span class="sxs-lookup"><span data-stu-id="f86d4-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> behavior, which will fix the problem:</span></span><pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f86d4-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f86d4-106">Name</span></span>    | <span data-ttu-id="f86d4-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="f86d4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f86d4-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="f86d4-108">Scope</span></span>   |<span data-ttu-id="f86d4-109">Mały</span><span class="sxs-lookup"><span data-stu-id="f86d4-109">Minor</span></span>|
|<span data-ttu-id="f86d4-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="f86d4-110">Version</span></span>|<span data-ttu-id="f86d4-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f86d4-111">4.5</span></span>|
|<span data-ttu-id="f86d4-112">Typ</span><span class="sxs-lookup"><span data-stu-id="f86d4-112">Type</span></span>|<span data-ttu-id="f86d4-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f86d4-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f86d4-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f86d4-114">Affected APIs</span></span>

- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)`

-->
