---
ms.openlocfilehash: ed669364efe9dd8f57d831a3764dd3fc68cd5e05
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496763"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="8a08c-101">Niewłaściwa obsługa wieloczęściowej ASP.NET może spowodować utratę danych formularza.</span><span class="sxs-lookup"><span data-stu-id="8a08c-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="8a08c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8a08c-102">Details</span></span>

<span data-ttu-id="8a08c-103">W aplikacjach, które są przeznaczone .NET Framework 4.7.2 i starszych wersji, ASP.Net może niepoprawnie analizować wieloczęściowe wartości graniczne, dzięki czemu dane formularza są niedostępne podczas wykonywania żądania.</span><span class="sxs-lookup"><span data-stu-id="8a08c-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.Net might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="8a08c-104">Aplikacje przeznaczone dla .NET Framework 4,8 lub nowszych wersji poprawnie analizują wieloczęściowe dane, dlatego wartości formularza są dostępne podczas wykonywania żądania.</span><span class="sxs-lookup"><span data-stu-id="8a08c-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8a08c-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="8a08c-105">Suggestion</span></span>

<span data-ttu-id="8a08c-106">Począwszy od aplikacji uruchomionych na .NET Framework 4,8, gdy element docelowy .NET Framework 4,8 lub nowszy przy użyciu <code>targetFrameworkVersion</code> elementu, domyślne zachowanie zostanie zmienione na ograniczniki paska.</span><span class="sxs-lookup"><span data-stu-id="8a08c-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="8a08c-107">Po przeznaczeniu do poprzednich wersji struktury lub nie używania <code>targetFrameworkVersion</code> , końcowe ograniczniki dla niektórych wartości są nadal zwracane. Takie zachowanie może być również jawnie kontrolowane za pomocą <code>appSetting</code> :</span><span class="sxs-lookup"><span data-stu-id="8a08c-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8a08c-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8a08c-108">Name</span></span>    | <span data-ttu-id="8a08c-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="8a08c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8a08c-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="8a08c-110">Scope</span></span>   |<span data-ttu-id="8a08c-111">Nieznane</span><span class="sxs-lookup"><span data-stu-id="8a08c-111">Unknown</span></span>|
|<span data-ttu-id="8a08c-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="8a08c-112">Version</span></span>|<span data-ttu-id="8a08c-113">4,8</span><span class="sxs-lookup"><span data-stu-id="8a08c-113">4.8</span></span>|
|<span data-ttu-id="8a08c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="8a08c-114">Type</span></span>|<span data-ttu-id="8a08c-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="8a08c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8a08c-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8a08c-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
