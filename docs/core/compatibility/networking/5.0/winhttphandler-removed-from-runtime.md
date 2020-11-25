---
title: 'Zmiana podziału: WinHttpHandler usunięty z środowiska uruchomieniowego platformy .NET'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie WinHttpHandler został usunięty z środowiska uruchomieniowego platformy .NET.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761435"
---
# <a name="winhttphandler-removed-from-net-runtime"></a>WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET

`WinHttpHandler`Klasa została usunięta z zestawu *System.Net.Http.dll* . Jest ona teraz dostępna tylko jako [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)poza pasmem (OOB).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna jako część podstawowych bibliotek .NET. Począwszy od platformy .NET 5,0, <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna tylko jako oddzielnie zainstalowany [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).

## <a name="recommended-action"></a>Zalecana akcja

Zainstaluj [pakiet NuGet system .NET. http. WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). Lub, jeśli nie są wymagane funkcje dotyczące usługi WinHTTP, użyj <xref:System.Net.Http.SocketsHttpHandler> zamiast tego.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
