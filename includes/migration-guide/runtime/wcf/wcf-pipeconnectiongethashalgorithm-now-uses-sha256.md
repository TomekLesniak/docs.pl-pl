---
ms.openlocfilehash: d32725b0d3063d3320b73e02039ff567090da932
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496359"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="80bc2-101">Funkcja WCF PipeConnection. GetHashAlgorithm używa teraz SHA256</span><span class="sxs-lookup"><span data-stu-id="80bc2-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="80bc2-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="80bc2-102">Details</span></span>

<span data-ttu-id="80bc2-103">Rozpoczynając od .NET Framework 4.7.1, Windows Communication Foundation używa skrótu SHA256 do generowania losowych nazw dla nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="80bc2-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="80bc2-104">W .NET Framework 4,7 i starszych wersjach użyto skrótu SHA1.</span><span class="sxs-lookup"><span data-stu-id="80bc2-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80bc2-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="80bc2-105">Suggestion</span></span>

<span data-ttu-id="80bc2-106">Jeśli wystąpi problem ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym, możesz go wycofać, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="80bc2-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="80bc2-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="80bc2-107">Name</span></span>    | <span data-ttu-id="80bc2-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="80bc2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80bc2-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="80bc2-109">Scope</span></span>   |<span data-ttu-id="80bc2-110">Mały</span><span class="sxs-lookup"><span data-stu-id="80bc2-110">Minor</span></span>|
|<span data-ttu-id="80bc2-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="80bc2-111">Version</span></span>|<span data-ttu-id="80bc2-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="80bc2-112">4.7.1</span></span>|
|<span data-ttu-id="80bc2-113">Typ</span><span class="sxs-lookup"><span data-stu-id="80bc2-113">Type</span></span>|<span data-ttu-id="80bc2-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="80bc2-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="80bc2-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="80bc2-115">Affected APIs</span></span>

<span data-ttu-id="80bc2-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="80bc2-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
