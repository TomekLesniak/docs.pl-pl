---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496870"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="f591c-101">ASP.NET MVC teraz wyprowadza spacje w ciągach przesyłanych za pośrednictwem parametrów trasy</span><span class="sxs-lookup"><span data-stu-id="f591c-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="f591c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f591c-102">Details</span></span>

<span data-ttu-id="f591c-103">Aby zapewnić zgodność ze standardem RFC 2396, w przypadku wypełniania parametrów akcji z trasy są teraz zmieniane spacje w ścieżkach tras.</span><span class="sxs-lookup"><span data-stu-id="f591c-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="f591c-104">W związku z tym, w  <code>/controller/action/some data</code> <code>/controller/action/{data}</code> przeciwieństwie do trasy i podania <code>some data</code> jako parametru danych, będzie ona teraz dostarczana <code>some%20data</code> .</span><span class="sxs-lookup"><span data-stu-id="f591c-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f591c-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f591c-105">Suggestion</span></span>

<span data-ttu-id="f591c-106">Kod powinien zostać zaktualizowany do nieucieczki parametrów ciągu z trasy.</span><span class="sxs-lookup"><span data-stu-id="f591c-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="f591c-107">Jeśli oryginalny identyfikator URI jest wymagany, dostęp do niego można uzyskać za pomocą <xref:System.Net.HttpWebRequest.RequestUri> . Interfejs API OriginalString.</span><span class="sxs-lookup"><span data-stu-id="f591c-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="f591c-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f591c-108">Name</span></span>    | <span data-ttu-id="f591c-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="f591c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f591c-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="f591c-110">Scope</span></span>   |<span data-ttu-id="f591c-111">Mały</span><span class="sxs-lookup"><span data-stu-id="f591c-111">Minor</span></span>|
|<span data-ttu-id="f591c-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="f591c-112">Version</span></span>|<span data-ttu-id="f591c-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f591c-113">4.5.2</span></span>|
|<span data-ttu-id="f591c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="f591c-114">Type</span></span>|<span data-ttu-id="f591c-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f591c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f591c-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f591c-116">Affected APIs</span></span>

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
