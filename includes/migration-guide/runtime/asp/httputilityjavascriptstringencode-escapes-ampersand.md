---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606263"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility. JavaScriptStringEncode — ucieczki

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> wyprowadza znak handlowego "i" ( &amp; ).

#### <a name="suggestion"></a>Sugestia

Jeśli aplikacja zależy od poprzedniego zachowania tej metody, można dodać ustawienie ASPNET: JavaScriptDoNotEncodeAmpersand do [elementu appSettings ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) w pliku konfiguracji.

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
