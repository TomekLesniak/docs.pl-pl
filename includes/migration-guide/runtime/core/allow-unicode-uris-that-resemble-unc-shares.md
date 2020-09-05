---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497340"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Zezwalaj na kodowanie Unicode w identyfikatorach URI, które przypominają udziały UNC

#### <a name="details"></a>Szczegóły

W programie <xref:System.Uri?displayProperty=fullName> konstruowanie identyfikatora URI pliku zawierającego zarówno nazwę udziału UNC, jak i znaki Unicode nie spowoduje już wystąpienia identyfikatora URI z nieprawidłowym stanem wewnętrznym. Zachowanie zmieni się tylko wtedy, gdy spełnione są wszystkie następujące warunki:<ul><li>Identyfikator URI ma schemat <code>file:</code> i ma cztery lub więcej ukośników.</li><li>Nazwa hosta zaczyna się od znaku podkreślenia lub innego niezastrzeżonego symbolu.</li><li>Identyfikator URI zawiera znaki Unicode.</li></ul>

#### <a name="suggestion"></a>Sugestia

Aplikacje korzystające z identyfikatorów URI spójnie zawierające kod Unicode mogą korzystać z tego zachowania, aby nie zezwalać na odwołania do udziałów UNC. Aplikacje te powinny być używane w <xref:System.Uri.IsUnc> zamian.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.7.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
