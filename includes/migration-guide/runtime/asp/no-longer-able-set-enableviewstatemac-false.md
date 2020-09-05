---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497255"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Nie można już ustawić EnableViewStateMac na FAŁSZ

#### <a name="details"></a>Szczegóły

ASP.NET nie pozwala już deweloperom na określanie <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> lub <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> . Kod uwierzytelniania komunikatów o stanie (MAC) jest teraz wymuszany dla wszystkich żądań z osadzonym stanem widoku. Dotyczy to tylko aplikacji, które jawnie ustawili Właściwość EnableViewStateMac <code>false</code> .

#### <a name="suggestion"></a>Sugestia

Należy przyjąć, że EnableViewStateMac należy mieć wartość true, a wszystkie wynikowe błędy w systemie MAC muszą zostać rozwiązane (jak wyjaśniono w [niniejszych wskazówkach](https://support.microsoft.com/kb/2915218), które zawierają wiele rozwiązań w zależności od tego, co powoduje błędy w przypadku komputerów Mac).

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4.5.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
