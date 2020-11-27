---
ms.openlocfilehash: 2819fb3857fa6d40a2b2e42eeaec2d9c6e50eef0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96299356"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autoryzacja: Przeciążenie metody addauthorization przeniesiono do innego zestawu

Nazwy podstawowych `AddAuthorization` metod, które były używane do znajdowania w programie, `Microsoft.AspNetCore.Authorization` zostały zmienione na `AddAuthorizationCore` . Stare `AddAuthorization` metody nadal istnieją, ale znajdują się w `Microsoft.AspNetCore.Authorization.Policy` zestawie. Aplikacje korzystające z obu tych metod powinny nie mieć wpływu. Należy pamiętać, że `Microsoft.AspNetCore.Authorization.Policy` teraz jest dostarczany w ramach udostępnionej platformy, a nie jako pakiet autonomiczny, zgodnie z opisem w sekcji [Shared Framework: zestawy usunięte z Microsoft. AspNetCore. app](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

`AddAuthorization` Metody istniały w `Microsoft.AspNetCore.Authorization` .

#### <a name="new-behavior"></a>Nowe zachowanie

`AddAuthorization` Metody istnieją w `Microsoft.AspNetCore.Authorization.Policy` . `AddAuthorizationCore` jest nową nazwą dla starych metod.

#### <a name="reason-for-change"></a>Przyczyna zmiany

`AddAuthorization` jest lepszą nazwą metody dodawania wszystkich typowych usług wymaganych do autoryzacji.

#### <a name="recommended-action"></a>Zalecana akcja

Dodaj odwołanie do `Microsoft.AspNetCore.Authorization.Policy` lub Użyj `AddAuthorizationCore` zamiast niego.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
