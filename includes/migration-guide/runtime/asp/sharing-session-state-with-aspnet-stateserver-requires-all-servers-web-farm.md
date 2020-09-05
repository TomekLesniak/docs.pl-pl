---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497788"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Udostępnianie stanu sesji przy użyciu Asp.Net StateServer wymaga, aby wszystkie serwery w kolektywie serwerów sieci Web używały tej samej wersji .NET Framework

#### <a name="details"></a>Szczegóły

Podczas włączania <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> stanu sesji wszystkie serwery w danej farmie sieci Web muszą używać tej samej wersji .NET Framework, aby zapewnić prawidłowe udostępnianie stanu.

#### <a name="suggestion"></a>Sugestia

Pamiętaj, aby uaktualnić .NET Framework wersje na serwerach sieci Web, które udostępniają stan w tym samym czasie.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
