---
ms.openlocfilehash: 0d38e2177377e7e9ea911071eb65aa13aa1f5900
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496675"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a>ustawienie aplikacji "DataAnnotations: DataTypeAttribute: disableRegEx" jest domyślnie włączone w .NET Framework 4.7.2

#### <a name="details"></a>Szczegóły

W .NET Framework 4.6.1 wprowadzono ustawienie aplikacji ( <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> ), które umożliwia użytkownikom wyłączenie używania wyrażeń regularnych w atrybutach typu danych (takich jak <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType> , <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> , i <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType> ). Dzięki temu można zmniejszyć luki w zabezpieczeniach, takie jak uniknięcie ataku typu "odmowa usługi" przy użyciu określonych wyrażeń regularnych.<br/>W .NET Framework 4.6.1 to ustawienie aplikacji wyłączające użycie wyrażenia regularnego zostało domyślnie ustawione na wartość <code>false</code> . Począwszy od .NET Framework 4.7.2, ten przełącznik konfiguracji jest domyślnie ustawiany, <code>true</code> Aby dodatkowo ograniczyć bezpieczną lukę w zabezpieczeniach aplikacji sieci Web przeznaczonych .NET Framework 4.7.2 i powyżej.

#### <a name="suggestion"></a>Sugestia

Jeśli okaże się, że wyrażenia regularne w aplikacji sieci Web nie działają po uaktualnieniu do .NET Framework 4.7.2, można zaktualizować wartość <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> Ustawienia, aby <code>false</code> przywrócić poprzednie zachowanie.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.7.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
