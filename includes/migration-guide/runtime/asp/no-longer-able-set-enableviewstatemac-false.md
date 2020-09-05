---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497255"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="b62d7-101">Nie można już ustawić EnableViewStateMac na FAŁSZ</span><span class="sxs-lookup"><span data-stu-id="b62d7-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="b62d7-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b62d7-102">Details</span></span>

<span data-ttu-id="b62d7-103">ASP.NET nie pozwala już deweloperom na określanie <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> lub <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> .</span><span class="sxs-lookup"><span data-stu-id="b62d7-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="b62d7-104">Kod uwierzytelniania komunikatów o stanie (MAC) jest teraz wymuszany dla wszystkich żądań z osadzonym stanem widoku.</span><span class="sxs-lookup"><span data-stu-id="b62d7-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="b62d7-105">Dotyczy to tylko aplikacji, które jawnie ustawili Właściwość EnableViewStateMac <code>false</code> .</span><span class="sxs-lookup"><span data-stu-id="b62d7-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b62d7-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b62d7-106">Suggestion</span></span>

<span data-ttu-id="b62d7-107">Należy przyjąć, że EnableViewStateMac należy mieć wartość true, a wszystkie wynikowe błędy w systemie MAC muszą zostać rozwiązane (jak wyjaśniono w [niniejszych wskazówkach](https://support.microsoft.com/kb/2915218), które zawierają wiele rozwiązań w zależności od tego, co powoduje błędy w przypadku komputerów Mac).</span><span class="sxs-lookup"><span data-stu-id="b62d7-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="b62d7-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b62d7-108">Name</span></span>    | <span data-ttu-id="b62d7-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="b62d7-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b62d7-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="b62d7-110">Scope</span></span>   |<span data-ttu-id="b62d7-111">Duży</span><span class="sxs-lookup"><span data-stu-id="b62d7-111">Major</span></span>|
|<span data-ttu-id="b62d7-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="b62d7-112">Version</span></span>|<span data-ttu-id="b62d7-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b62d7-113">4.5.2</span></span>|
|<span data-ttu-id="b62d7-114">Typ</span><span class="sxs-lookup"><span data-stu-id="b62d7-114">Type</span></span>|<span data-ttu-id="b62d7-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b62d7-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b62d7-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b62d7-116">Affected APIs</span></span>

<span data-ttu-id="b62d7-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="b62d7-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
