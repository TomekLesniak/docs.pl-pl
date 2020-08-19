---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608467"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET

`WinHttpHandler`Klasa została usunięta z zestawu *System.Net.Http.dll* . Jest ona teraz dostępna tylko jako [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)poza pasmem (OOB).

#### <a name="version-introduced"></a>Wprowadzona wersja

5.0

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna jako część podstawowych bibliotek .NET. Począwszy od platformy .NET 5,0, <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna tylko jako oddzielnie zainstalowany [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).

#### <a name="recommended-action"></a>Zalecana akcja

Zainstaluj [pakiet NuGet system .NET. http. WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). Lub, jeśli nie są wymagane funkcje dotyczące usługi WinHTTP, użyj <xref:System.Net.Http.SocketsHttpHandler> zamiast tego.

#### <a name="category"></a>Kategoria

Networking

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
