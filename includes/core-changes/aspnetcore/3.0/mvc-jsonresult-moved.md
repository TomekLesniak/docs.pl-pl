---
ms.openlocfilehash: 96c2a32dd7cca91e965601d715bbd4625bba439a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032839"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult przeniesiony do Microsoft. AspNetCore. MVC. Core

`JsonResult` został przeniesiony do `Microsoft.AspNetCore.Mvc.Core` zestawu. Ten typ jest używany do definiowania w [Microsoft.AspNetCore.Mvc.Formatters.Jsna](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Dodano atrybut na poziomie zestawu [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) , aby `Microsoft.AspNetCore.Mvc.Formatters.Json` rozwiązać ten problem w przypadku większości użytkowników. Aplikacje korzystające z bibliotek innych firm mogą napotkać problemy.

#### <a name="version-introduced"></a>Wprowadzona wersja

3,0 wersja zapoznawcza 6

#### <a name="old-behavior"></a>Stare zachowanie

Aplikacja używająca pomyślnie utworzonych bibliotek opartych na 2,2.

#### <a name="new-behavior"></a>Nowe zachowanie

Kompilacja nie powiedzie się w aplikacji korzystającej z biblioteki opartej na 2,2. Wystąpił błąd zawierający odmianę następującego tekstu:

```output
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Przykład takiego problemu można znaleźć w temacie [dotnet/aspnetcore # 7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Przyczyna zmiany

Zmiany na poziomie platformy do kompozycji ASP.NET Core zgodnie z opisem w polu [ASPNET/anonse # 325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Zalecana akcja

Biblioteki skompilowane w wersji 2,2 programu `Microsoft.AspNetCore.Mvc.Formatters.Json` mogą wymagać ponownej kompilacji w celu rozwiązania problemu dla wszystkich klientów. Jeśli to dotyczy, skontaktuj się z autorem biblioteki. Poproś o ponowną kompilację biblioteki do celu ASP.NET Core 3,0.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
