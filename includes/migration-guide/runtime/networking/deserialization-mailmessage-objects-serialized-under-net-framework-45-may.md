---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497596"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Deserializacja serializowanych obiektów MailMessage w .NET Framework 4,5 może zakończyć się niepowodzeniem

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, <xref:System.Web.Mail.MailMessage> obiekty mogą zawierać znaki inne niż ASCII. W .NET Framework 4 obsługiwane są tylko znaki ASCII. <xref:System.Web.Mail.MailMessage> obiekty, które zawierają znaki inne niż ASCII i które są serializowane w .NET Framework 4,5 lub nowszej, nie mogą być deserializowane w .NET Framework 4.

#### <a name="suggestion"></a>Sugestia

Upewnij się, że kod zapewnia obsługę wyjątków podczas deserializacji <xref:System.Web.Mail.MailMessage> obiektu.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->
