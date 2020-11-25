---
title: 'Zmiana podziału: uwierzytelnianie: AzureAD. UI i AzureADB2C. interfejs API i pakiety oznaczone jako przestarzałe'
description: 'Dowiedz się więcej na temat istotnej zmiany w ASP.NET Core 5,0 zatytułowanym uwierzytelnianie: AzureAD. UI i AzureADB2C. interfejs API i pakiety oznaczone jako przestarzałe'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c977ba4d6e34fc5f11133bdd1446a94d54efcb63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761667"
---
# <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>Uwierzytelnianie: AzureAD. UI i AzureADB2C. interfejs API i pakiety oznaczone jako przestarzałe

W ASP.NET Core 2,1 Integracja z uwierzytelnianiem za pomocą usługi Azure Active Directory (Azure AD) i Azure Active Directory B2C (Azure AD B2C) jest zapewniana przez pakiety [Microsoft. AspNetCore. Authentication. AzureAD. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) i [Microsoft. AspNetCore. Authentication. AzureADB2C. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) . Funkcje udostępniane przez te pakiety są oparte na punkcie końcowym usługi Azure AD v 1.0.

W ASP.NET Core 5,0 i nowszych integrację z usługą Azure AD i uwierzytelnianiem Azure AD B2C są udostępniane przez pakiet [Microsoft. Identity. Web](https://www.nuget.org/packages/Microsoft.Identity.Web) . Ten pakiet jest oparty na platformie tożsamości firmy Microsoft, która jest znana wcześniej jako punkt końcowy usługi Azure AD v 2.0. W związku z tym stare interfejsy API w `Microsoft.AspNetCore.Authentication.AzureAD.UI` `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` pakietach i były przestarzałe.

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25807](https://github.com/dotnet/aspnetcore/issues/25807).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

## <a name="old-behavior"></a>Stare zachowanie

Interfejsy API nie zostały oznaczone jako przestarzałe.

## <a name="new-behavior"></a>Nowe zachowanie

Interfejsy API są oznaczone jako przestarzałe.

## <a name="reason-for-change"></a>Przyczyna zmiany

Funkcje uwierzytelniania usługi Azure AD i Azure AD B2C zostały zmigrowane do interfejsów API Microsoft Authentication Library (MSAL), które są dostępne w programie `Microsoft.Identity.Web` .

## <a name="recommended-action"></a>Zalecana akcja

Postępuj zgodnie ze `Microsoft.Identity.Web` wskazówkami interfejsu API dotyczącymi [aplikacji sieci Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) i [interfejsów API sieci Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).

## <a name="affected-apis"></a>Dotyczy interfejsów API

* [Microsoft. AspNetCore. Authentication. AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft. AspNetCore. Authentication. AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
