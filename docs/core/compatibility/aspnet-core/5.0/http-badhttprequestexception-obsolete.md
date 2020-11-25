---
title: 'Nieprzerwana zmiana: HTTP: Kestrel i IIS BadHttpRequestException typy oznaczone jako przestarzałe i zastąpione'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej HTTP: Kestrel i typy BadHttpRequestException IIS oznaczone jako przestarzałe i zastąpione'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761472"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>HTTP: Kestrel i IIS BadHttpRequestException typy oznaczone jako przestarzałe i zastąpione

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i zostały `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` oznaczone jako przestarzałe i zmienione na pochodne od `Microsoft.AspNetCore.Http.BadHttpRequestException` . Serwery Kestrel i IIS nadal generują stare typy wyjątków w celu zapewnienia zgodności z poprzednimi wersjami. Przestarzałe typy zostaną usunięte w przyszłej wersji.

Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 20614](https://github.com/dotnet/aspnetcore/issues/20614).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 4

## <a name="old-behavior"></a>Stare zachowanie

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` pochodzące od <xref:System.IO.IOException?displayProperty=nameWithType> .

## <a name="new-behavior"></a>Nowe zachowanie

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` są przestarzałe. Typy pochodzą z `Microsoft.AspNetCore.Http.BadHttpRequestException` , które pochodzą z `System.IO.IOException` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Wprowadzono zmianę w:

* Konsolidowanie zduplikowanych typów.
* Ujednolicenie zachowania między implementacjami serwera.

Aplikacja może teraz przechwycić wyjątek podstawowy `Microsoft.AspNetCore.Http.BadHttpRequestException` podczas korzystania z usługi Kestrel lub IIS.

## <a name="recommended-action"></a>Zalecana akcja

Zamień Użycie elementów `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` na `Microsoft.AspNetCore.Http.BadHttpRequestException` .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- [Microsoft. AspNetCore. Server. IIS. BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft. AspNetCore. Server. Kestrel. BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
