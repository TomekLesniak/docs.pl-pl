---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032696"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Autoryzacja: implementacje IAuthorizationPolicyProvider wymagają nowej metody

W ASP.NET Core 3,0 `GetFallbackPolicyAsync` dodano nową metodę do `IAuthorizationPolicyProvider` . Te zasady powrotu są używane przez oprogramowanie pośredniczące autoryzacji, gdy nie określono zasad.

Aby uzyskać więcej informacji, zobacz [dotnet/aspnetcore # 9759](https://github.com/dotnet/aspnetcore/pull/9759).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

Implementacje `IAuthorizationPolicyProvider` nie wymagały `GetFallbackPolicyAsync` metody.

#### <a name="new-behavior"></a>Nowe zachowanie

Implementacje `IAuthorizationPolicyProvider` wymagają `GetFallbackPolicyAsync` metody.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Nowa metoda była wymagana do `AuthorizationMiddleware` użycia w przypadku, gdy nie określono żadnych zasad.

#### <a name="recommended-action"></a>Zalecana akcja

Dodaj `GetFallbackPolicyAsync` metodę do implementacji programu `IAuthorizationPolicyProvider` .

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
