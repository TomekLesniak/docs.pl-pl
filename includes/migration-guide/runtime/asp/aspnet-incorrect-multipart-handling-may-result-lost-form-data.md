---
ms.openlocfilehash: d61a3b3dd855d783d7bff7cb74e5b84969e60860
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608054"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>Niewłaściwa obsługa wieloczęściowej ASP.NET może spowodować utratę danych formularza.

#### <a name="details"></a>Szczegóły

W aplikacjach, które są przeznaczone .NET Framework 4.7.2 i starszych wersji, ASP.NET może niepoprawnie analizować wieloczęściowe wartości graniczne, dzięki czemu dane formularza są niedostępne podczas wykonywania żądania. Aplikacje przeznaczone dla .NET Framework 4,8 lub nowszych wersji poprawnie analizują wieloczęściowe dane, dlatego wartości formularza są dostępne podczas wykonywania żądania.

#### <a name="suggestion"></a>Sugestia

Począwszy od aplikacji uruchomionych na .NET Framework 4,8, gdy element docelowy .NET Framework 4,8 lub nowszy przy użyciu <code>targetFrameworkVersion</code> elementu, domyślne zachowanie zostanie zmienione na ograniczniki paska. Po przeznaczeniu do poprzednich wersji struktury lub nie używania <code>targetFrameworkVersion</code> , końcowe ograniczniki dla niektórych wartości są nadal zwracane. Takie zachowanie może być również jawnie kontrolowane za pomocą <code>appSetting</code> :<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Nieznane|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
