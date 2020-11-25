---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032791"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Tożsamość: Konstruktor SignInManager akceptuje nowy parametr

Począwszy od ASP.NET Core 3,0, `IUserConfirmation<TUser>` do konstruktora został dodany nowy parametr `SignInManager` . Aby uzyskać więcej informacji, zobacz [dotnet/aspnetcore # 8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="reason-for-change"></a>Przyczyna zmiany

Celem zmiany było dodanie obsługi nowych przepływów poczty e-mail/potwierdzenia w tożsamości.

#### <a name="recommended-action"></a>Zalecana akcja

W przypadku ręcznego konstruowania `SignInManager` , należy podać implementację `IUserConfirmation` lub pobrać jeden z iniekcji zależności, aby zapewnić.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
