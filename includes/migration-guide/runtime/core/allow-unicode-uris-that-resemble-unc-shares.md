---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497340"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="95ac2-101">Zezwalaj na kodowanie Unicode w identyfikatorach URI, które przypominają udziały UNC</span><span class="sxs-lookup"><span data-stu-id="95ac2-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="95ac2-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="95ac2-102">Details</span></span>

<span data-ttu-id="95ac2-103">W programie <xref:System.Uri?displayProperty=fullName> konstruowanie identyfikatora URI pliku zawierającego zarówno nazwę udziału UNC, jak i znaki Unicode nie spowoduje już wystąpienia identyfikatora URI z nieprawidłowym stanem wewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="95ac2-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="95ac2-104">Zachowanie zmieni się tylko wtedy, gdy spełnione są wszystkie następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="95ac2-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="95ac2-105">Identyfikator URI ma schemat <code>file:</code> i ma cztery lub więcej ukośników.</span><span class="sxs-lookup"><span data-stu-id="95ac2-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="95ac2-106">Nazwa hosta zaczyna się od znaku podkreślenia lub innego niezastrzeżonego symbolu.</span><span class="sxs-lookup"><span data-stu-id="95ac2-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="95ac2-107">Identyfikator URI zawiera znaki Unicode.</span><span class="sxs-lookup"><span data-stu-id="95ac2-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="95ac2-108">Sugestia</span><span class="sxs-lookup"><span data-stu-id="95ac2-108">Suggestion</span></span>

<span data-ttu-id="95ac2-109">Aplikacje korzystające z identyfikatorów URI spójnie zawierające kod Unicode mogą korzystać z tego zachowania, aby nie zezwalać na odwołania do udziałów UNC.</span><span class="sxs-lookup"><span data-stu-id="95ac2-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="95ac2-110">Aplikacje te powinny być używane w <xref:System.Uri.IsUnc> zamian.</span><span class="sxs-lookup"><span data-stu-id="95ac2-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="95ac2-111">Nazwa</span><span class="sxs-lookup"><span data-stu-id="95ac2-111">Name</span></span>    | <span data-ttu-id="95ac2-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="95ac2-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="95ac2-113">Zakres</span><span class="sxs-lookup"><span data-stu-id="95ac2-113">Scope</span></span>   |<span data-ttu-id="95ac2-114">Edge</span><span class="sxs-lookup"><span data-stu-id="95ac2-114">Edge</span></span>|
|<span data-ttu-id="95ac2-115">Wersja</span><span class="sxs-lookup"><span data-stu-id="95ac2-115">Version</span></span>|<span data-ttu-id="95ac2-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="95ac2-116">4.7.2</span></span>|
|<span data-ttu-id="95ac2-117">Typ</span><span class="sxs-lookup"><span data-stu-id="95ac2-117">Type</span></span>|<span data-ttu-id="95ac2-118">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="95ac2-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="95ac2-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="95ac2-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
