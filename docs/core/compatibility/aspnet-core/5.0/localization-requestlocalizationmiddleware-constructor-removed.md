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
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a>Lokalizacja: przestarzały Konstruktor został usunięty z oprogramowania pośredniczącego w lokalizacji żądania

<xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>Konstruktor, który <xref:Microsoft.Extensions.Logging.ILoggerFactory> nie ma parametru, został oznaczony jako przestarzały [w tym zatwierdzeniu](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0). W ASP.NET Core 5,0 przestarzały Konstruktor został usunięty. Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 23785](https://github.com/dotnet/aspnetcore/issues/23785).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

## <a name="old-behavior"></a>Stare zachowanie

Istnieje przestarzały `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` Konstruktor.

## <a name="new-behavior"></a>Nowe zachowanie

Przestarzały `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` Konstruktor nie istnieje.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana zapewnia, że oprogramowanie pośredniczące żądania ma zawsze dostęp do rejestratora.

## <a name="recommended-action"></a>Zalecana akcja

Podczas ręcznego konstruowania wystąpienia `RequestLocalizationMiddleware` , należy przekazać `ILoggerFactory` wystąpienie w konstruktorze. Jeśli prawidłowe `ILoggerFactory` wystąpienie jest niedostępne w tym kontekście, rozważ przekazanie konstruktora oprogramowania pośredniczącego <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> wystąpieniem.

## <a name="affected-apis"></a>Dotyczy interfejsów API

[RequestLocalizationMiddleware. ctor (RequestDelegate, IOptions \<RequestLocalizationOptions> )](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
