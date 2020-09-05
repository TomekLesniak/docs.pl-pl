---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496155"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="dd2e1-101">Metoda replace w adresach URL usługi OData jest domyślnie wyłączona</span><span class="sxs-lookup"><span data-stu-id="dd2e1-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="dd2e1-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="dd2e1-102">Details</span></span>

<span data-ttu-id="dd2e1-103">Począwszy od .NET Framework 4,5, Metoda replace w adresach URL usługi OData jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="dd2e1-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="dd2e1-104">Gdy funkcja zamiany OData jest wyłączona (teraz domyślnie), wszelkie żądania użytkowników, w tym funkcje Replace (rzadko występujące), zakończą się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="dd2e1-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dd2e1-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="dd2e1-105">Suggestion</span></span>

<span data-ttu-id="dd2e1-106">Jeśli Metoda replace jest wymagana (co jest nietypowe), można ją zmienić za pomocą ustawień konfiguracji ( <xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="dd2e1-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="dd2e1-107">Jednak włączona Metoda replace może otwierać luki w zabezpieczeniach i być używana tylko po dokładnym przeglądzie.</span><span class="sxs-lookup"><span data-stu-id="dd2e1-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="dd2e1-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="dd2e1-108">Name</span></span>    | <span data-ttu-id="dd2e1-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="dd2e1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dd2e1-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="dd2e1-110">Scope</span></span>   |<span data-ttu-id="dd2e1-111">Edge</span><span class="sxs-lookup"><span data-stu-id="dd2e1-111">Edge</span></span>|
|<span data-ttu-id="dd2e1-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="dd2e1-112">Version</span></span>|<span data-ttu-id="dd2e1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="dd2e1-113">4.5</span></span>|
|<span data-ttu-id="dd2e1-114">Typ</span><span class="sxs-lookup"><span data-stu-id="dd2e1-114">Type</span></span>|<span data-ttu-id="dd2e1-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="dd2e1-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dd2e1-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="dd2e1-116">Affected APIs</span></span>

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
