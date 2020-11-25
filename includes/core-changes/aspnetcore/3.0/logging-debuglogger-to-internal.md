---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032823"
---
### <a name="logging-debuglogger-class-made-internal"></a>Rejestrowanie: Klasa DebugLogger wykonana wewnętrznie

Przed ASP.NET Core 3,0, `DebugLogger` modyfikator dostępu był `public` . W ASP.NET Core 3,0 modyfikator dostępu został zmieniony na `internal` .

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="reason-for-change"></a>Przyczyna zmiany

Trwa zmiana:

* Wymuś spójność z innymi implementacjami rejestratora, takimi jak `ConsoleLogger` .
* Zmniejsz powierzchnię interfejsu API.

#### <a name="recommended-action"></a>Zalecana akcja

Użyj <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` metody rozszerzenia, aby włączyć rejestrowanie debugowania. <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> jest również nadal `public` w przypadku, gdy usługa musi zostać zarejestrowana ręcznie.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
