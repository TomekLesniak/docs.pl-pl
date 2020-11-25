---
title: 'Nieprzerwana zmiana: Kestrel: protokół HTTP/2 jest wyłączony przy użyciu protokołu TLS w niezgodnych wersjach systemu Windows'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Kestrel: HTTP/2 wyłączonej przy użyciu protokołu TLS dla niezgodnych wersji systemu Windows'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761592"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a>Kestrel: protokół HTTP/2 został wyłączony przy użyciu protokołu TLS dla niezgodnych wersji systemu Windows

Aby włączyć protokół HTTP/2 dla Transport Layer Security (TLS) w systemie Windows, należy spełnić dwa wymagania:

- Obsługa negocjacji protokołów Application-Layer (CLIENTHELLO ALPN), która jest dostępna od Windows 8.1 i Windows Server 2012 R2.
- Zestaw szyfrów zgodny z protokołem HTTP/2, który jest dostępny od systemu Windows 10 i Windows Server 2016.

W związku z tym zachowanie Kestrel w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS zostało zmienione na:

- Obniżanie `Http1` poziomu i rejestrowanie komunikatów na `Information` poziomie, gdy [ListenOptions. HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) jest ustawiony na `Http1AndHttp2` . `Http1AndHttp2` jest wartością domyślną dla `ListenOptions.HttpProtocols` .
- Zgłoś, `NotSupportedException` gdy `ListenOptions.HttpProtocols` jest ustawiony na `Http2` .

Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 23068](https://github.com/dotnet/aspnetcore/issues/23068).

## <a name="version-introduced"></a>Wprowadzona wersja

ASP.NET Core 5,0 wersja zapoznawcza 7

## <a name="old-behavior"></a>Stare zachowanie

W poniższej tabeli przedstawiono zachowanie w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS.

| Protokoły | System Windows 7,<br />Windows Server 2008 R2,<br />lub starszy | System Windows 8,<br />Windows Server 2012 | Windows 8.1<br />Windows Server 2012 z dodatkiem R2 | System Windows 10,<br />System Windows Server 2016,<br />lub nowszy |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Generować `NotSupportedException`                   | Błąd podczas uzgadniania protokołu TLS     | Błąd podczas uzgadniania protokołu TLS &ast;     | Brak błędów |
| `Http1AndHttp2` | Obniżanie poziomu `Http1`                    | Obniżanie poziomu `Http1`     | Błąd podczas uzgadniania protokołu TLS &ast;     | Brak błędów |

&ast; Skonfiguruj zgodne mechanizmy szyfrowania, aby włączyć te scenariusze.

## <a name="new-behavior"></a>Nowe zachowanie

W poniższej tabeli przedstawiono zachowanie w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS.

| Protokoły | System Windows 7,<br />Windows Server 2008 R2,<br />lub starszy | System Windows 8,<br />Windows Server 2012 | Windows 8.1<br />Windows Server 2012 z dodatkiem R2 | System Windows 10,<br />System Windows Server 2016,<br />lub nowszy |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Generować `NotSupportedException`                   | Generować `NotSupportedException`     | Zgłoś `NotSupportedException`&ast;&ast;     | Brak błędów |
| `Http1AndHttp2` | Obniżanie poziomu `Http1`                    | Obniżanie poziomu `Http1`     | `Http1`Obniżanie poziomu&ast;&ast;     | Brak błędów |

&ast;&ast; Skonfiguruj zgodne mechanizmy szyfrowania i ustaw przełącznik kontekstu aplikacji, `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` Aby `true` włączyć te scenariusze.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana zapewnia, że błędy zgodności dla protokołu HTTP/2 za pośrednictwem protokołu TLS w starszych wersjach systemu Windows są roznoszone jako wczesne i możliwie jasne.

## <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że protokół HTTP/2 przy użyciu protokołu TLS jest wyłączony w niezgodnych wersjach systemu Windows. Windows 8.1 i Windows Server 2012 R2 są niezgodne, ponieważ nie mają domyślnie wymaganych szyfrów. Można jednak zaktualizować ustawienia konfiguracji komputera w taki sposób, aby korzystały z szyfrów zgodnych z protokołem HTTP/2. Aby uzyskać więcej informacji, zobacz [mechanizmy szyfrowania TLS w Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1). Po skonfigurowaniu protokołu HTTP/2 za pośrednictwem protokołu TLS w systemie Kestrel należy włączyć ustawienie przełącznika kontekstu aplikacji `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` . Na przykład:

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

Żadna podstawowa pomoc techniczna nie została zmieniona. Na przykład protokół HTTP/2 za pośrednictwem protokołu TLS nigdy nie pracował w systemie Windows 8 lub Windows Server 2012. Ta zmiana modyfikuje sposób wyświetlania błędów w tych nieobsługiwanych scenariuszach.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
