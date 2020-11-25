---
title: 'Nieprzerwana zmiana: usługi IIS: UrlRewrite ciągi zapytań oprogramowania pośredniczącego są zachowywane'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej IIS: UrlRewrite ciągi zapytań oprogramowania pośredniczącego są zachowywane'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761348"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: UrlRewrite ciągi zapytania oprogramowania pośredniczącego są zachowywane

Usterka oprogramowania pośredniczącego usług IIS UrlRewrite uniemożliwiła zachowywanie ciągu zapytania w regułach ponownego zapisywania. Ta usterka została naprawiona w celu zachowania spójności z zachowaniem modułu UrlRewrite IIS.

Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 22972](https://github.com/dotnet/aspnetcore/issues/22972).

## <a name="version-introduced"></a>Wprowadzona wersja

ASP.NET Core 5,0 wersja zapoznawcza 7

## <a name="old-behavior"></a>Stare zachowanie

Weź pod uwagę następujące zasady ponownego zapisywania:

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

Poprzednia reguła nie dołącza ciągu zapytania. Identyfikator URI, taki jak `/about?id=1` przekieruje do `/contact` , zamiast `/contact?id=1` . `appendQueryString`Atrybut jest również domyślnie `true` .

## <a name="new-behavior"></a>Nowe zachowanie

Ciąg zapytania jest zachowywany. Identyfikator URI z przykładu w [starym zachowaniu](#old-behavior) będzie miał wartość `/contact?id=1` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Stare zachowanie nie jest zgodne z zachowaniem modułu UrlRewrite IIS. Do obsługi portów między programami i modułem pośredniczącym celem jest zachowanie spójnych zachowań.

## <a name="recommended-action"></a>Zalecana akcja

Jeśli preferowane jest zachowanie usunięcia ciągu zapytania, należy ustawić `action` element na `appendQueryString="false"` .

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
