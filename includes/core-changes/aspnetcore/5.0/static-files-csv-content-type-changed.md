---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391185"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="08166-101">Pliki statyczne: typ zawartości CSV został zmieniony na zgodny ze standardami</span><span class="sxs-lookup"><span data-stu-id="08166-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="08166-102">W ASP.NET Core 5,0 `Content-Type` wartość domyślna nagłówka odpowiedzi, która jest stosowana przez [oprogramowanie pośredniczące plików statycznych](/aspnet/core/fundamentals/static-files) dla plików *CSV* , została zmieniona na wartość zgodną ze standardami `text/csv` .</span><span class="sxs-lookup"><span data-stu-id="08166-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="08166-103">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 17385](https://github.com/dotnet/AspNetCore/issues/17385).</span><span class="sxs-lookup"><span data-stu-id="08166-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="08166-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="08166-104">Version introduced</span></span>

<span data-ttu-id="08166-105">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="08166-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="08166-106">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="08166-106">Old behavior</span></span>

<span data-ttu-id="08166-107">`Content-Type`Użyto wartości nagłówka `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="08166-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="08166-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="08166-108">New behavior</span></span>

<span data-ttu-id="08166-109">`Content-Type`Wartość nagłówka `text/csv` jest używana.</span><span class="sxs-lookup"><span data-stu-id="08166-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="08166-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="08166-110">Reason for change</span></span>

<span data-ttu-id="08166-111">Zgodność ze standardem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) .</span><span class="sxs-lookup"><span data-stu-id="08166-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="08166-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="08166-112">Recommended action</span></span>

<span data-ttu-id="08166-113">Jeśli ta zmiana ma wpływ na aplikację, można dostosować mapowanie typu rozszerzenia pliku do MIME.</span><span class="sxs-lookup"><span data-stu-id="08166-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="08166-114">Aby powrócić do `application/octet-stream` typu MIME, należy zmodyfikować <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> wywołanie metody w `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="08166-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="08166-115">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="08166-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="08166-116">Aby uzyskać więcej informacji na temat dostosowywania mapowania, zobacz [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="08166-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="08166-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="08166-117">Category</span></span>

<span data-ttu-id="08166-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="08166-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="08166-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="08166-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
