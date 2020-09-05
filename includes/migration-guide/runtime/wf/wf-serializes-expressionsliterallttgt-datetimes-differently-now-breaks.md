---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496487"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="42200-101">Funkcja WF serializować wyrażenia. literały &lt; T &gt; datetimes są teraz inaczej (dzieli Niestandardowe analizatory języka XAML)</span><span class="sxs-lookup"><span data-stu-id="42200-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="42200-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="42200-102">Details</span></span>

<span data-ttu-id="42200-103">Skojarzony <xref:System.Windows.Markup.ValueSerializer> obiekt spowoduje przekonwertowanie <xref:System.DateTime?displayProperty=fullName> obiektu lub, <xref:System.DateTimeOffset?displayProperty=fullName> którego sekunda i <xref:System.DateTime.Millisecond?displayProperty=fullName> składniki są inne niż zero i (dla <xref:System.DateTime?displayProperty=fullName> wartości), których <xref:System.DateTime.Kind> Właściwość nie została określona jako składnia elementu właściwości zamiast ciągu.</span><span class="sxs-lookup"><span data-stu-id="42200-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="42200-104">Ta zmiana umożliwia <xref:System.DateTime?displayProperty=fullName> i <xref:System.DateTimeOffset?displayProperty=fullName> wartości, które mają być okrężne.</span><span class="sxs-lookup"><span data-stu-id="42200-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="42200-105">Niestandardowe analizatory języka XAML, które zakładają, że wejściowy kod XAML znajduje się w składni atrybutów, nie będą działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="42200-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="42200-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="42200-106">Suggestion</span></span>

<span data-ttu-id="42200-107">Ta zmiana umożliwia <xref:System.DateTime?displayProperty=fullName> i <xref:System.DateTimeOffset?displayProperty=fullName> wartości, które mają być okrężne.</span><span class="sxs-lookup"><span data-stu-id="42200-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="42200-108">Niestandardowe analizatory języka XAML, które zakładają, że wejściowy kod XAML znajduje się w składni atrybutów, nie będą działać poprawnie.</span><span class="sxs-lookup"><span data-stu-id="42200-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="42200-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="42200-109">Name</span></span>    | <span data-ttu-id="42200-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="42200-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="42200-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="42200-111">Scope</span></span>   |<span data-ttu-id="42200-112">Edge</span><span class="sxs-lookup"><span data-stu-id="42200-112">Edge</span></span>|
|<span data-ttu-id="42200-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="42200-113">Version</span></span>|<span data-ttu-id="42200-114">4.5</span><span class="sxs-lookup"><span data-stu-id="42200-114">4.5</span></span>|
|<span data-ttu-id="42200-115">Typ</span><span class="sxs-lookup"><span data-stu-id="42200-115">Type</span></span>|<span data-ttu-id="42200-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="42200-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="42200-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="42200-117">Affected APIs</span></span>

<span data-ttu-id="42200-118">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="42200-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
