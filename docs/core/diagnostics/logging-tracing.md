---
title: Rejestrowanie i śledzenie — .NET Core
description: Wprowadzenie do rejestrowania i śledzenia w programie .NET Core.
ms.date: 10/12/2020
ms.openlocfilehash: 33c78ecc839b552267ad43dd00b7d627e756a939
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997698"
---
# <a name="net-core-logging-and-tracing"></a>Rejestrowanie i śledzenie w programie .NET Core

Rejestrowanie i śledzenie są bardzo dwie nazwy dla tej samej techniki. Prosta technika została użyta od momentu wczesnego dnia komputerów. Po prostu obejmuje instrumentację aplikacji w celu zapisania danych wyjściowych do późniejszego wykorzystania.

## <a name="reasons-to-use-logging-and-tracing"></a>Przyczyny używania rejestrowania i śledzenia

Ta prosta technika jest Surprisingly zaawansowana. Może być używana w sytuacjach, w których debuger kończy się niepowodzeniem:

- Problemy występujące w długim okresie czasu mogą być trudne do debugowania przy użyciu tradycyjnego debugera. Dzienniki pozwalają na szczegółowe przeglądy po dłuższym okresie. Z kolei debugery są ograniczone do analizy w czasie rzeczywistym.
- Aplikacje wielowątkowe i aplikacje rozproszone często są trudne do debugowania.  Dołączanie debugera powoduje modyfikację zachowań. Szczegółowe dzienniki można analizować w miarę potrzeby, aby zrozumieć złożone systemy.
- Problemy w aplikacjach rozproszonych mogą powstać w wyniku złożonej interakcji między wieloma składnikami i może nie być uzasadnione, aby podłączyć debuger do każdej części systemu.
- Nie należy zawiesić wielu usług. Dołączanie debugera często powoduje błędy limitu czasu.
- Problemy nie są zawsze obsługiwane. Rejestrowanie i śledzenie zostało zaprojektowane z myślą o niskim obciążeniu, dzięki czemu program może zawsze rejestrować się w przypadku wystąpienia problemu.

## <a name="net-core-apis"></a>Interfejsy API platformy .NET Core

### <a name="print-style-apis"></a>Interfejsy API stylu drukowania

<xref:System.Console?displayProperty=nameWithType>Klasy, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> i, <xref:System.Diagnostics.Debug?displayProperty=nameWithType> każdy udostępniają podobne interfejsy API stylu drukowania wygodne do rejestrowania.

Wybór interfejsu API drukowania stylu do użycia. Kluczowe różnice są następujące:

- <xref:System.Console?displayProperty=nameWithType>
  - Zawsze włączone i zawsze zapisuje się w konsoli programu.
  - Przydatne w przypadku informacji, które mogą być wymagane przez klienta w wersji.
  - Ponieważ jest to najprostszy sposób, często jest używany do tymczasowego debugowania ad hoc. Ten kod debugowania często nigdy nie jest sprawdzany w kontroli źródła.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - Włączone tylko wtedy, gdy `TRACE` jest zdefiniowany.
  - Domyślnie zapisy do załączenia <xref:System.Diagnostics.Trace.Listeners> <xref:System.Diagnostics.DefaultTraceListener> .
  - Użyj tego interfejsu API podczas tworzenia dzienników, które będą włączone w większości kompilacji.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - Włączone tylko wtedy, gdy `DEBUG` jest zdefiniowany.
  - Zapisuje do dołączonego debugera.
  - Przy `*nix` zapisie do stderr, jeśli `COMPlus_DebugWriteToStdErr` jest ustawiona.
  - Użyj tego interfejsu API podczas tworzenia dzienników, które będą włączone tylko w kompilacjach debugowania.

### <a name="logging-events"></a>Rejestrowanie zdarzeń

Poniższe interfejsy API są bardziej zorientowane na zdarzenia. Zamiast rejestrowania prostych ciągów rejestruje obiekty zdarzeń.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource jest podstawowym głównym interfejsem API śledzenia programu .NET Core.
  - Dostępne we wszystkich wersjach .NET Standard.
  - Umożliwia tylko śledzenie obiektów, które można serializować.
  - Zapisuje dane w podłączonych [detektorach zdarzeń](xref:System.Diagnostics.Tracing.EventListener).
  - Platforma .NET Core udostępnia detektory dla:
    - EventPipe platformy .NET Core na wszystkich platformach
    - [Śledzenie zdarzeń systemu Windows (ETW)](/windows/win32/etw/event-tracing-portal)
    - [LTTng — struktura śledzenia dla systemu Linux](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - Zawarte w oprogramowaniu .NET Core i jako [pakiet NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) dla .NET Framework.
  - Umożliwia śledzenie w procesie obiektów, które nie są możliwe do serializacji.
  - Zawiera mostek umożliwiający Zapisywanie wybranych pól zarejestrowanych obiektów w usłudze <xref:System.Diagnostics.Tracing.EventSource> .

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - Przedstawia ostateczny sposób identyfikowania komunikatów dziennika pochodzących z określonego działania lub transakcji. Ten obiekt może służyć do skorelowania dzienników w różnych usługach.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Tylko system Windows.
  - Zapisuje komunikaty w dzienniku zdarzeń systemu Windows.
  - Administratorzy systemu oczekują krytycznych komunikatów o błędach aplikacji w dzienniku zdarzeń systemu Windows.

## <a name="ilogger-and-logging-frameworks"></a>ILogger i struktury rejestrowania

Interfejsy API niskiego poziomu mogą nie być właściwym wyborem dla potrzeb rejestrowania. Warto rozważyć strukturę rejestrowania.

<xref:Microsoft.Extensions.Logging.ILogger>Interfejs został użyty do utworzenia wspólnego interfejsu rejestrowania, w którym rejestratory mogą być wstawiane przez iniekcję zależności.

Na przykład, aby umożliwić wybranie najlepszego wyboru dla aplikacji .NET, zapewnia obsługę wybranych platform wbudowanych i innych firm:

- [Dostawcy wbudowanego rejestrowania platformy .NET](../extensions/logging-providers.md#built-in-logging-providers)
- [Dostawcy rejestrowania .NET innych firm](../extensions/logging-providers.md#third-party-logging-providers)

## <a name="logging-related-references"></a>Rejestrowanie powiązanych odwołań

- [Instrukcje: Kompilowanie warunkowe ze śledzeniem i debugowaniem](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [Instrukcje: Dodawanie instrukcji śledzenia do kodu aplikacji](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- [Rejestrowanie w programie .NET](../extensions/logging.md) zawiera omówienie technik rejestrowania, które obsługuje.

- [Interpolacja ciągów języka C#](../../csharp/language-reference/tokens/interpolated.md) może uprościć pisanie kodu rejestrowania.

- <xref:System.Exception.Message?displayProperty=nameWithType>Właściwość jest przydatna do rejestrowania wyjątków.

- <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType>Klasa może być przydatna do dostarczania informacji o stosie w dziennikach.

## <a name="performance-considerations"></a>Zagadnienia dotyczące wydajności

Formatowanie ciągu może mieć zauważalny czas przetwarzania procesora CPU.

W przypadku aplikacji o krytycznym znaczeniu zaleca się:

- Unikaj wielu rejestracji, gdy nikt nie nasłuchuje. Unikaj konstruowania kosztownych komunikatów rejestrowania, sprawdzając, czy rejestrowanie jest włączone jako pierwsze.
- Rejestruj tylko to, co jest przydatne.
- Odłóż ozdobne formatowanie do etapu analizy.
