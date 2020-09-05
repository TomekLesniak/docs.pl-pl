---
ms.openlocfilehash: 8964cd2f69e95e4078001997ad5a5d126ce42d7b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497578"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Poprawa powiązania danych dla elementu prebindingcollection

#### <a name="details"></a>Szczegóły

Naprawiono <xref:System.Windows.Data.Binding> nieprawidłowe użycie indeksatora IList, gdy obiekt źródłowy deklaruje niestandardowy indeksator o tym samym podpisie (na przykład, &lt; TItemcollection int, niestandardowa &gt; ).

#### <a name="suggestion"></a>Sugestia

Aby można było korzystać z tej zmiany w aplikacji, która jest przeznaczona dla starszej wersji, należy ją uruchomić w .NET Framework 4,8 lub nowszej i musimy zadecydować o zmianie, dodając następujący [przełącznik AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) do <code>&lt;runtime&gt;</code> sekcji pliku konfiguracyjnego aplikacji i ustawiając go na <code>false</code> :<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
