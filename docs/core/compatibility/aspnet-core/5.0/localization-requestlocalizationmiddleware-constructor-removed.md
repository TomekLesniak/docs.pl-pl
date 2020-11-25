---
title: 'Istotna zmiana: Lokalizacja: przestarzały Konstruktor został usunięty w przypadku oprogramowania pośredniczącego w lokalizacji żądania'
description: 'Dowiedz się więcej o istotnej zmianie w 5,0 ASP.NET Core lokalizacji zatytułowanej: przestarzały Konstruktor został usunięty z oprogramowania pośredniczącego żądania'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761643"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="5f31d-103">Lokalizacja: przestarzały Konstruktor został usunięty z oprogramowania pośredniczącego w lokalizacji żądania</span><span class="sxs-lookup"><span data-stu-id="5f31d-103">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="5f31d-104"><xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>Konstruktor, który <xref:Microsoft.Extensions.Logging.ILoggerFactory> nie ma parametru, został oznaczony jako przestarzały [w tym zatwierdzeniu](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span><span class="sxs-lookup"><span data-stu-id="5f31d-104">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="5f31d-105">W ASP.NET Core 5,0 przestarzały Konstruktor został usunięty.</span><span class="sxs-lookup"><span data-stu-id="5f31d-105">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="5f31d-106">Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="5f31d-106">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5f31d-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="5f31d-107">Version introduced</span></span>

<span data-ttu-id="5f31d-108">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="5f31d-108">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5f31d-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="5f31d-109">Old behavior</span></span>

<span data-ttu-id="5f31d-110">Istnieje przestarzały `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="5f31d-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5f31d-111">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="5f31d-111">New behavior</span></span>

<span data-ttu-id="5f31d-112">Przestarzały `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` Konstruktor nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="5f31d-112">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5f31d-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="5f31d-113">Reason for change</span></span>

<span data-ttu-id="5f31d-114">Ta zmiana zapewnia, że oprogramowanie pośredniczące żądania ma zawsze dostęp do rejestratora.</span><span class="sxs-lookup"><span data-stu-id="5f31d-114">This change ensures that the request localization middleware always has access to a logger.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5f31d-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="5f31d-115">Recommended action</span></span>

<span data-ttu-id="5f31d-116">Podczas ręcznego konstruowania wystąpienia `RequestLocalizationMiddleware` , należy przekazać `ILoggerFactory` wystąpienie w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="5f31d-116">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="5f31d-117">Jeśli prawidłowe `ILoggerFactory` wystąpienie jest niedostępne w tym kontekście, rozważ przekazanie konstruktora oprogramowania pośredniczącego <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="5f31d-117">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5f31d-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5f31d-118">Affected APIs</span></span>

[<span data-ttu-id="5f31d-119">RequestLocalizationMiddleware. ctor (RequestDelegate, IOptions \<RequestLocalizationOptions> )</span><span class="sxs-lookup"><span data-stu-id="5f31d-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
