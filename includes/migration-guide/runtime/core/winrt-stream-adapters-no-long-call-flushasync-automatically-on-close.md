---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497292"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="9b206-101">Karty strumienia WinRT nie są długie wywołania FlushAsync automatycznie przy zamykaniu</span><span class="sxs-lookup"><span data-stu-id="9b206-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="9b206-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="9b206-102">Details</span></span>

<span data-ttu-id="9b206-103">W aplikacjach ze sklepu Windows środowisko wykonawcze systemu Windows karty usługi Stream nie wywołują już metody FlushAsync z metody Dispose.</span><span class="sxs-lookup"><span data-stu-id="9b206-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b206-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="9b206-104">Suggestion</span></span>

<span data-ttu-id="9b206-105">Ta zmiana powinna być niewidoczna.</span><span class="sxs-lookup"><span data-stu-id="9b206-105">This change should be transparent.</span></span> <span data-ttu-id="9b206-106">Deweloperzy mogą przywrócić poprzednie zachowanie, pisząc kod podobny do tego:</span><span class="sxs-lookup"><span data-stu-id="9b206-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="9b206-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="9b206-107">Name</span></span>    | <span data-ttu-id="9b206-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="9b206-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b206-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="9b206-109">Scope</span></span>   |<span data-ttu-id="9b206-110">Przezroczyste</span><span class="sxs-lookup"><span data-stu-id="9b206-110">Transparent</span></span>|
|<span data-ttu-id="9b206-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="9b206-111">Version</span></span>|<span data-ttu-id="9b206-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="9b206-112">4.5.1</span></span>|
|<span data-ttu-id="9b206-113">Typ</span><span class="sxs-lookup"><span data-stu-id="9b206-113">Type</span></span>|<span data-ttu-id="9b206-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="9b206-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9b206-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9b206-115">Affected APIs</span></span>

<span data-ttu-id="9b206-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9b206-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
