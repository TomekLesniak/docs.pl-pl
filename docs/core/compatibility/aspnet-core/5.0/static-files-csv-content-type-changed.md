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
# <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="37b37-103">Pliki statyczne: typ zawartości CSV został zmieniony na zgodny ze standardami</span><span class="sxs-lookup"><span data-stu-id="37b37-103">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="37b37-104">W ASP.NET Core 5,0 `Content-Type` wartość domyślna nagłówka odpowiedzi, która jest stosowana przez [oprogramowanie pośredniczące plików statycznych](/aspnet/core/fundamentals/static-files) dla plików *CSV* , została zmieniona na wartość zgodną ze standardami `text/csv` .</span><span class="sxs-lookup"><span data-stu-id="37b37-104">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="37b37-105">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 17385](https://github.com/dotnet/AspNetCore/issues/17385).</span><span class="sxs-lookup"><span data-stu-id="37b37-105">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="37b37-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="37b37-106">Version introduced</span></span>

<span data-ttu-id="37b37-107">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="37b37-107">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="37b37-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="37b37-108">Old behavior</span></span>

<span data-ttu-id="37b37-109">`Content-Type`Użyto wartości nagłówka `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="37b37-109">The `Content-Type` header value `application/octet-stream` was used.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="37b37-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="37b37-110">New behavior</span></span>

<span data-ttu-id="37b37-111">`Content-Type`Wartość nagłówka `text/csv` jest używana.</span><span class="sxs-lookup"><span data-stu-id="37b37-111">The `Content-Type` header value `text/csv` is used.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="37b37-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="37b37-112">Reason for change</span></span>

<span data-ttu-id="37b37-113">Zgodność ze standardem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) .</span><span class="sxs-lookup"><span data-stu-id="37b37-113">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="37b37-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="37b37-114">Recommended action</span></span>

<span data-ttu-id="37b37-115">Jeśli ta zmiana ma wpływ na aplikację, można dostosować mapowanie typu rozszerzenia pliku do MIME.</span><span class="sxs-lookup"><span data-stu-id="37b37-115">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="37b37-116">Aby powrócić do `application/octet-stream` typu MIME, należy zmodyfikować <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> wywołanie metody w `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="37b37-116">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="37b37-117">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="37b37-117">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="37b37-118">Aby uzyskać więcej informacji na temat dostosowywania mapowania, zobacz [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="37b37-118">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="37b37-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="37b37-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
