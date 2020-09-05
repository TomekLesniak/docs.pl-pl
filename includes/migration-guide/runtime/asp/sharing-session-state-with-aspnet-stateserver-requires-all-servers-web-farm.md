---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497788"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="b596e-101">Udostępnianie stanu sesji przy użyciu Asp.Net StateServer wymaga, aby wszystkie serwery w kolektywie serwerów sieci Web używały tej samej wersji .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b596e-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="b596e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b596e-102">Details</span></span>

<span data-ttu-id="b596e-103">Podczas włączania <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> stanu sesji wszystkie serwery w danej farmie sieci Web muszą używać tej samej wersji .NET Framework, aby zapewnić prawidłowe udostępnianie stanu.</span><span class="sxs-lookup"><span data-stu-id="b596e-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b596e-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b596e-104">Suggestion</span></span>

<span data-ttu-id="b596e-105">Pamiętaj, aby uaktualnić .NET Framework wersje na serwerach sieci Web, które udostępniają stan w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="b596e-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="b596e-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b596e-106">Name</span></span>    | <span data-ttu-id="b596e-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="b596e-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b596e-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="b596e-108">Scope</span></span>   |<span data-ttu-id="b596e-109">Edge</span><span class="sxs-lookup"><span data-stu-id="b596e-109">Edge</span></span>|
|<span data-ttu-id="b596e-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="b596e-110">Version</span></span>|<span data-ttu-id="b596e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="b596e-111">4.5</span></span>|
|<span data-ttu-id="b596e-112">Typ</span><span class="sxs-lookup"><span data-stu-id="b596e-112">Type</span></span>|<span data-ttu-id="b596e-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b596e-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b596e-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b596e-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
