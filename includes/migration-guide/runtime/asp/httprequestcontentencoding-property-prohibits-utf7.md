---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497214"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>Właściwość HttpRequest. ContentEncoding zabrania UTF7

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, kodowanie UTF-7 jest zabronione w <xref:System.Web.HttpRequest?displayProperty=fullName> treści "s". Dane dla aplikacji, które zależą od danych przychodzących w formacie UTF-7, nie będą poprawnie dekodowane w niektórych przypadkach.

#### <a name="suggestion"></a>Sugestia

W idealnym przypadku aplikacje należy zaktualizować tak, aby nie korzystały z kodowania UTF-7 w <xref:System.Web.HttpRequest?displayProperty=fullName> s. Alternatywnie można przywrócić starsze zachowanie przy użyciu <code>aspnet:AllowUtf7RequestContentEncoding</code> atrybutu [AppSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) elementu.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
