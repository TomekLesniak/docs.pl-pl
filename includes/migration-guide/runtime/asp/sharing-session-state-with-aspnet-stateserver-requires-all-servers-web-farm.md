---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609140"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="3a8d8-101">Udostępnianie stanu sesji przy użyciu ASP.NET StateServer wymaga, aby wszystkie serwery w kolektywie serwerów sieci Web używały tej samej wersji .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a8d8-101">Sharing session state with ASP.NET StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="3a8d8-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3a8d8-102">Details</span></span>

<span data-ttu-id="3a8d8-103">Podczas włączania <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> stanu sesji wszystkie serwery w danej farmie sieci Web muszą używać tej samej wersji .NET Framework, aby zapewnić prawidłowe udostępnianie stanu.</span><span class="sxs-lookup"><span data-stu-id="3a8d8-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a8d8-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3a8d8-104">Suggestion</span></span>

<span data-ttu-id="3a8d8-105">Pamiętaj, aby uaktualnić .NET Framework wersje na serwerach sieci Web, które udostępniają stan w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="3a8d8-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="3a8d8-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3a8d8-106">Name</span></span>    | <span data-ttu-id="3a8d8-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="3a8d8-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a8d8-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="3a8d8-108">Scope</span></span>   |<span data-ttu-id="3a8d8-109">Edge</span><span class="sxs-lookup"><span data-stu-id="3a8d8-109">Edge</span></span>|
|<span data-ttu-id="3a8d8-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="3a8d8-110">Version</span></span>|<span data-ttu-id="3a8d8-111">4.5</span><span class="sxs-lookup"><span data-stu-id="3a8d8-111">4.5</span></span>|
|<span data-ttu-id="3a8d8-112">Typ</span><span class="sxs-lookup"><span data-stu-id="3a8d8-112">Type</span></span>|<span data-ttu-id="3a8d8-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3a8d8-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a8d8-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3a8d8-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
