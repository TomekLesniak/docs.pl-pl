---
ms.openlocfilehash: 55a26f1ab27792cbedf3f31b797f37d3f768d51a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497898"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>ASP.NET Rozwiązywanie problemów z obsługą InputAttributes i LabelAttributes dla kontrolki CheckBox dla formularzy WebForms

#### <a name="details"></a>Szczegóły

W przypadku aplikacji przeznaczonych do .NET Framework 4.7.2 i starszych wersji, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> które są programowo dodawane do formantu WebForms, <xref:System.Web.UI.WebControls.CheckBox> są tracone po odświeżeniu. W przypadku aplikacji przeznaczonych do .NET Framework 4,8 lub nowszych wersji są one zachowywane po odświeżeniu.

#### <a name="suggestion"></a>Sugestia

Aby mieć poprawne zachowanie w zakresie przywracania atrybutów na stronie ogłaszania zwrotnego, ustaw wartość <code>targetFrameworkVersion</code> na 4,8 lub wyższą. Przykład:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Ustawienie go na niższym poziomie lub w ogóle zachowuje stare nieprawidłowe zachowanie.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Nieznane|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.UI.WebControls.CheckBox`

-->
