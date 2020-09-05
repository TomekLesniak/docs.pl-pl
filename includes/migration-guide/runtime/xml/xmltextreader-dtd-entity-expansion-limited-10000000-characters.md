---
ms.openlocfilehash: e56d896f093d6cd28ed0d6640ba154e5d4593c6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497184"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="a9c6e-101">Rozwinięcie jednostki DTD XmlTextReader jest ograniczone do 10 000 000 znaków</span><span class="sxs-lookup"><span data-stu-id="a9c6e-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="a9c6e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a9c6e-102">Details</span></span>

<span data-ttu-id="a9c6e-103">Rozwinięcie jednostki DTD jest teraz ograniczone do 10 000 000 znaków.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="a9c6e-104">Możliwość ładowania plików XML bez rozszerzenia jednostki DTD lub z możliwością ograniczonego rozszerzania jednostki DTD pozostaje bez zmian.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="a9c6e-105">Nie można ładować plików z jednostkami DTD, które są rozszerzane do ponad 10 000 000 znaków. Zostanie zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a9c6e-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="a9c6e-106">Suggestion</span></span>

<span data-ttu-id="a9c6e-107">Jeśli limit rozwinięcia jednostki DTD jest zbyt niski 10 000 000, wartość można zastąpić <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> właściwością.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="a9c6e-108"><xref:System.Xml.XmlReaderSettings?displayProperty=fullName>Z prawidłową <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> wartością można przesłać do elementu <code>XmlReader.Create</code> , który ma <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (IE). <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)></span><span class="sxs-lookup"><span data-stu-id="a9c6e-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="a9c6e-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="a9c6e-109">Name</span></span>    | <span data-ttu-id="a9c6e-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="a9c6e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a9c6e-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="a9c6e-111">Scope</span></span>   |<span data-ttu-id="a9c6e-112">Edge</span><span class="sxs-lookup"><span data-stu-id="a9c6e-112">Edge</span></span>|
|<span data-ttu-id="a9c6e-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="a9c6e-113">Version</span></span>|<span data-ttu-id="a9c6e-114">4.5</span><span class="sxs-lookup"><span data-stu-id="a9c6e-114">4.5</span></span>|
|<span data-ttu-id="a9c6e-115">Typ</span><span class="sxs-lookup"><span data-stu-id="a9c6e-115">Type</span></span>|<span data-ttu-id="a9c6e-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="a9c6e-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a9c6e-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a9c6e-117">Affected APIs</span></span>

- <xref:System.Xml.XmlTextReader?displayProperty=nameWithType>
- <xref:System.Xml.XmlTextReader.%23ctor>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)>

<!--

#### Affected APIs

- `T:System.Xml.XmlTextReader`
- `M:System.Xml.XmlTextReader.#ctor`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.Xml.XmlNameTable)`

-->
