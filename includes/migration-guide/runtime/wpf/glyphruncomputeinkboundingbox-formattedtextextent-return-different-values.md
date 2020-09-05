---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496412"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="d6ed4-101">GlyphRun. ComputeInkBoundingBox () i FormattedText. zakres zwracają różne wartości zaczynające się na .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="d6ed4-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="d6ed4-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d6ed4-102">Details</span></span>

<span data-ttu-id="d6ed4-103">Wprowadzono ulepszenia <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> i <xref:System.Windows.Media.FormattedText.Extent> w .NET Framework 4,5 do rozwiązywania problemów, gdy pola są zbyt małe dla zawartych symboli w niektórych przypadkach w .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="d6ed4-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="d6ed4-104">W wyniku tego niektóre pola ograniczające będą większe od początku .NET Framework 4,5, co spowodowało delikatne różnice w układzie interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d6ed4-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d6ed4-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d6ed4-105">Suggestion</span></span>

<span data-ttu-id="d6ed4-106">Należy pamiętać, że niektóre rozmiary pól ograniczających glify zostały powiększone.</span><span class="sxs-lookup"><span data-stu-id="d6ed4-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="d6ed4-107">Te zmiany zwykle ulepszają testowanie i pole trafień, ale jeśli jest wymagane zachowanie starsze (pre-.NET 4,5), można je dodać, dodając następujący wpis do pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="d6ed4-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d6ed4-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d6ed4-108">Name</span></span>    | <span data-ttu-id="d6ed4-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="d6ed4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6ed4-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="d6ed4-110">Scope</span></span>   |<span data-ttu-id="d6ed4-111">Edge</span><span class="sxs-lookup"><span data-stu-id="d6ed4-111">Edge</span></span>|
|<span data-ttu-id="d6ed4-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="d6ed4-112">Version</span></span>|<span data-ttu-id="d6ed4-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d6ed4-113">4.5</span></span>|
|<span data-ttu-id="d6ed4-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d6ed4-114">Type</span></span>|<span data-ttu-id="d6ed4-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d6ed4-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d6ed4-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d6ed4-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
