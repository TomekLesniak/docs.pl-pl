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
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="61d0a-103">HTTP: Kestrel i IIS BadHttpRequestException typy oznaczone jako przestarzałe i zastąpione</span><span class="sxs-lookup"><span data-stu-id="61d0a-103">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="61d0a-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i zostały `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` oznaczone jako przestarzałe i zmienione na pochodne od `Microsoft.AspNetCore.Http.BadHttpRequestException` .</span><span class="sxs-lookup"><span data-stu-id="61d0a-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="61d0a-105">Serwery Kestrel i IIS nadal generują stare typy wyjątków w celu zapewnienia zgodności z poprzednimi wersjami.</span><span class="sxs-lookup"><span data-stu-id="61d0a-105">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="61d0a-106">Przestarzałe typy zostaną usunięte w przyszłej wersji.</span><span class="sxs-lookup"><span data-stu-id="61d0a-106">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="61d0a-107">Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="61d0a-107">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="61d0a-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="61d0a-108">Version introduced</span></span>

<span data-ttu-id="61d0a-109">5,0 wersja zapoznawcza 4</span><span class="sxs-lookup"><span data-stu-id="61d0a-109">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="61d0a-110">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="61d0a-110">Old behavior</span></span>

<span data-ttu-id="61d0a-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` pochodzące od <xref:System.IO.IOException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="61d0a-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="61d0a-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="61d0a-112">New behavior</span></span>

<span data-ttu-id="61d0a-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="61d0a-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="61d0a-114">Typy pochodzą z `Microsoft.AspNetCore.Http.BadHttpRequestException` , które pochodzą z `System.IO.IOException` .</span><span class="sxs-lookup"><span data-stu-id="61d0a-114">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="61d0a-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="61d0a-115">Reason for change</span></span>

<span data-ttu-id="61d0a-116">Wprowadzono zmianę w:</span><span class="sxs-lookup"><span data-stu-id="61d0a-116">The change was made to:</span></span>

* <span data-ttu-id="61d0a-117">Konsolidowanie zduplikowanych typów.</span><span class="sxs-lookup"><span data-stu-id="61d0a-117">Consolidate duplicate types.</span></span>
* <span data-ttu-id="61d0a-118">Ujednolicenie zachowania między implementacjami serwera.</span><span class="sxs-lookup"><span data-stu-id="61d0a-118">Unify behavior across server implementations.</span></span>

<span data-ttu-id="61d0a-119">Aplikacja może teraz przechwycić wyjątek podstawowy `Microsoft.AspNetCore.Http.BadHttpRequestException` podczas korzystania z usługi Kestrel lub IIS.</span><span class="sxs-lookup"><span data-stu-id="61d0a-119">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="61d0a-120">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="61d0a-120">Recommended action</span></span>

<span data-ttu-id="61d0a-121">Zamień Użycie elementów `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` i `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` na `Microsoft.AspNetCore.Http.BadHttpRequestException` .</span><span class="sxs-lookup"><span data-stu-id="61d0a-121">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="61d0a-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="61d0a-122">Affected APIs</span></span>

- [<span data-ttu-id="61d0a-123">Microsoft. AspNetCore. Server. IIS. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="61d0a-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="61d0a-124">Microsoft. AspNetCore. Server. Kestrel. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="61d0a-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
