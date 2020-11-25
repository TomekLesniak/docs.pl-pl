---
title: 'Nieprzerwana zmiana: pliki statyczne: typ zawartości woluminu CSV został zmieniony na zgodny ze standardami'
description: 'Dowiedz się więcej na temat istotnej zmiany w ASP.NET Core 5,0 zatytułowanych pliki statyczne: typ zawartości woluminu CSV został zmieniony na zgodny ze standardami'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c94a0cf213970d20559b7c061d8be220b43961e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761708"
---
# <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Pliki statyczne: typ zawartości CSV został zmieniony na zgodny ze standardami

W ASP.NET Core 5,0 `Content-Type` wartość domyślna nagłówka odpowiedzi, która jest stosowana przez [oprogramowanie pośredniczące plików statycznych](/aspnet/core/fundamentals/static-files) dla plików *CSV* , została zmieniona na wartość zgodną ze standardami `text/csv` .

Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 17385](https://github.com/dotnet/AspNetCore/issues/17385).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

## <a name="old-behavior"></a>Stare zachowanie

`Content-Type`Użyto wartości nagłówka `application/octet-stream` .

## <a name="new-behavior"></a>Nowe zachowanie

`Content-Type`Wartość nagłówka `text/csv` jest używana.

## <a name="reason-for-change"></a>Przyczyna zmiany

Zgodność ze standardem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) .

## <a name="recommended-action"></a>Zalecana akcja

Jeśli ta zmiana ma wpływ na aplikację, można dostosować mapowanie typu rozszerzenia pliku do MIME. Aby powrócić do `application/octet-stream` typu MIME, należy zmodyfikować <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> wywołanie metody w `Startup.Configure` . Na przykład:

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

Aby uzyskać więcej informacji na temat dostosowywania mapowania, zobacz [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
