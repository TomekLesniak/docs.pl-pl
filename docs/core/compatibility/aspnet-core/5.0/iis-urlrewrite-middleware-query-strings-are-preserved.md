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
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="89c16-103">IIS: UrlRewrite ciągi zapytania oprogramowania pośredniczącego są zachowywane</span><span class="sxs-lookup"><span data-stu-id="89c16-103">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="89c16-104">Usterka oprogramowania pośredniczącego usług IIS UrlRewrite uniemożliwiła zachowywanie ciągu zapytania w regułach ponownego zapisywania.</span><span class="sxs-lookup"><span data-stu-id="89c16-104">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="89c16-105">Ta usterka została naprawiona w celu zachowania spójności z zachowaniem modułu UrlRewrite IIS.</span><span class="sxs-lookup"><span data-stu-id="89c16-105">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="89c16-106">Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="89c16-106">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="89c16-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="89c16-107">Version introduced</span></span>

<span data-ttu-id="89c16-108">ASP.NET Core 5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="89c16-108">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="89c16-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="89c16-109">Old behavior</span></span>

<span data-ttu-id="89c16-110">Weź pod uwagę następujące zasady ponownego zapisywania:</span><span class="sxs-lookup"><span data-stu-id="89c16-110">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="89c16-111">Poprzednia reguła nie dołącza ciągu zapytania.</span><span class="sxs-lookup"><span data-stu-id="89c16-111">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="89c16-112">Identyfikator URI, taki jak `/about?id=1` przekieruje do `/contact` , zamiast `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="89c16-112">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="89c16-113">`appendQueryString`Atrybut jest również domyślnie `true` .</span><span class="sxs-lookup"><span data-stu-id="89c16-113">The `appendQueryString` attribute defaults to `true` as well.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="89c16-114">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="89c16-114">New behavior</span></span>

<span data-ttu-id="89c16-115">Ciąg zapytania jest zachowywany.</span><span class="sxs-lookup"><span data-stu-id="89c16-115">The query string is preserved.</span></span> <span data-ttu-id="89c16-116">Identyfikator URI z przykładu w [starym zachowaniu](#old-behavior) będzie miał wartość `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="89c16-116">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="89c16-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="89c16-117">Reason for change</span></span>

<span data-ttu-id="89c16-118">Stare zachowanie nie jest zgodne z zachowaniem modułu UrlRewrite IIS.</span><span class="sxs-lookup"><span data-stu-id="89c16-118">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="89c16-119">Do obsługi portów między programami i modułem pośredniczącym celem jest zachowanie spójnych zachowań.</span><span class="sxs-lookup"><span data-stu-id="89c16-119">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="89c16-120">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="89c16-120">Recommended action</span></span>

<span data-ttu-id="89c16-121">Jeśli preferowane jest zachowanie usunięcia ciągu zapytania, należy ustawić `action` element na `appendQueryString="false"` .</span><span class="sxs-lookup"><span data-stu-id="89c16-121">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="89c16-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="89c16-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
