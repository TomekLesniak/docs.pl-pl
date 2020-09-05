---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496622"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Deserializacja obiektów w domenach AppDomain może zakończyć się niepowodzeniem

#### <a name="details"></a>Szczegóły

W niektórych przypadkach, gdy aplikacja używa dwóch lub większej liczby domen aplikacji z różnymi bazami aplikacji, próba deserializacji obiektów w kontekście wywołania logicznego między domenami aplikacji zgłasza wyjątek.

#### <a name="suggestion"></a>Sugestia

Zobacz [łagodzenie: deserializacja obiektów w domenach aplikacji](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
