---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609140"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Udostępnianie stanu sesji przy użyciu ASP.NET StateServer wymaga, aby wszystkie serwery w kolektywie serwerów sieci Web używały tej samej wersji .NET Framework

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
