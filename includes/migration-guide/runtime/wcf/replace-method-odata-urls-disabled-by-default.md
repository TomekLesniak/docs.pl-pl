---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496155"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Metoda replace w adresach URL usługi OData jest domyślnie wyłączona

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, Metoda replace w adresach URL usługi OData jest domyślnie wyłączona. Gdy funkcja zamiany OData jest wyłączona (teraz domyślnie), wszelkie żądania użytkowników, w tym funkcje Replace (rzadko występujące), zakończą się niepowodzeniem.

#### <a name="suggestion"></a>Sugestia

Jeśli Metoda replace jest wymagana (co jest nietypowe), można ją zmienić za pomocą ustawień konfiguracji ( <xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName> ). Jednak włączona Metoda replace może otwierać luki w zabezpieczeniach i być używana tylko po dokładnym przeglądzie.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
