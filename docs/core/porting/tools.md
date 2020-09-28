---
title: Narzędzia do przenoszenia do platformy .NET Core
description: Dowiedz się więcej na temat niektórych narzędzi, których można użyć do przenoszenia do programu .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406131"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Narzędzia pomagające przenosić kod na platformę .NET Core

Narzędzia wymienione w tym artykule mogą okazać się przydatne podczas przenoszenia:

- [Analizator przenośności .NET](../../standard/analyzers/portability-analyzer.md) — łańcucha narzędzi, który może generować raport dotyczący sposobu, w jaki przenośny kod jest między .NET Framework i .NET Core:
  - Jako [Narzędzie wiersza polecenia](https://github.com/Microsoft/dotnet-apiport/releases)
  - Jako [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Analizator zgodności platformy](../../standard/analyzers/platform-compat-analyzer.md) — Analizator Roslyny, który informuje deweloperów, gdy używają interfejsów API specyficznych dla platformy z witryn wywołań, w których interfejs API może być niedostępny.
- Analizator [interfejsów API platformy .NET](../../standard/analyzers/api-analyzer.md) — Roslyn, który może pomóc w wykrywaniu problemów ze zgodnością platformy w aplikacjach i bibliotekach dla wielu platform.
- [try-Convert](https://www.nuget.org/packages/try-convert/) -narzędzie globalne platformy .NET Core, które może przekonwertować projekt lub całe rozwiązanie do zestawu .NET SDK, w tym przenieść aplikacje klasyczne do platformy .NET Core. Nie jest to zalecane, jeśli istnieje bardziej skomplikowana kompilacja (na przykład zadania niestandardowe, obiekty docelowe lub Importy), która odrzuca wiele typów projektów niezgodnych z platformą .NET Core.
