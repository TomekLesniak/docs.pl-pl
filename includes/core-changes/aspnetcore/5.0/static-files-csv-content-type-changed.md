---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391185"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Pliki statyczne: typ zawartości CSV został zmieniony na zgodny ze standardami

W ASP.NET Core 5,0 `Content-Type` wartość domyślna nagłówka odpowiedzi, która jest stosowana przez [oprogramowanie pośredniczące plików statycznych](/aspnet/core/fundamentals/static-files) dla plików *CSV* , została zmieniona na wartość zgodną ze standardami `text/csv` .

Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 17385](https://github.com/dotnet/AspNetCore/issues/17385).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

#### <a name="old-behavior"></a>Stare zachowanie

`Content-Type`Użyto wartości nagłówka `application/octet-stream` .

#### <a name="new-behavior"></a>Nowe zachowanie

`Content-Type`Wartość nagłówka `text/csv` jest używana.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Zgodność ze standardem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) .

#### <a name="recommended-action"></a>Zalecana akcja

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

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
