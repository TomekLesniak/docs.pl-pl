---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022973"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a>Oprogramowanie pośredniczące: oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi

Przed ASP.NET Core 5,0, [oprogramowanie pośredniczące obsługi wyjątków](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) wykonuje skonfigurowany program obsługi wyjątków, gdy wystąpił wyjątek. Jeśli program obsługi wyjątków skonfigurowany za pośrednictwem <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> nie zostanie znaleziony, zostanie wygenerowana odpowiedź HTTP 404. Odpowiedź jest myląca w ten sposób:

* Prawdopodobnie jest to błąd użytkownika.
* Zasłania fakt, że na serwerze wystąpił wyjątek.

Aby rozwiązać błąd mylący w ASP.NET Core 5,0, `ExceptionHandlerMiddleware` zgłasza oryginalny wyjątek, jeśli nie można odnaleźć programu obsługi wyjątków. W związku z tym serwer jest generowany odpowiedzi HTTP 500. Odpowiedź będzie łatwiejsza do sprawdzenia w dziennikach serwera podczas debugowania błędu, który wystąpił.

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25288](https://github.com/dotnet/aspnetcore/issues/25288).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC 1

#### <a name="old-behavior"></a>Stare zachowanie

Oprogramowanie pośredniczące obsługi wyjątków generuje odpowiedź HTTP 404, jeśli nie można znaleźć skonfigurowanej procedury obsługi wyjątków.

#### <a name="new-behavior"></a>Nowe zachowanie

Oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie można odnaleźć skonfigurowanej procedury obsługi wyjątków.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Błąd HTTP 404 nie sprawiają, że na serwerze wystąpił wyjątek. Ta zmiana powoduje błąd HTTP 500, aby oczywiste, że:

* Problem nie jest spowodowany błędem użytkownika.
* Na serwerze wystąpił wyjątek.

#### <a name="recommended-action"></a>Zalecana akcja

Brak zmian interfejsu API. Wszystkie istniejące aplikacje będą nadal kompilowane i uruchamiane. Zgłoszony wyjątek jest obsługiwany przez serwer. Na przykład wyjątek jest konwertowany na odpowiedź na błąd HTTP 500 przez [Kestrel](/aspnet/core/fundamentals/servers/kestrel) lub [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

#### Affected APIs

Not detectable via API analysis

-->
