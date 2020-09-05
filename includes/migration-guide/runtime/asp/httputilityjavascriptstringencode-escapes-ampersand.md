---
ms.openlocfilehash: 12fb72d5ee9fc0d6c57899589cb2b0da7db41f4a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496296"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility. JavaScriptStringEncode — ucieczki

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> wyprowadza znak handlowego "i" ( &amp; ).

#### <a name="suggestion"></a>Sugestia

Jeśli aplikacja zależy od poprzedniego zachowania tej metody, można dodać ustawienie ASPNET: JavaScriptDoNotEncodeAmpersand do [elementu appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) w pliku konfiguracji.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
