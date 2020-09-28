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
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="1036f-103">Narzędzia pomagające przenosić kod na platformę .NET Core</span><span class="sxs-lookup"><span data-stu-id="1036f-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="1036f-104">Narzędzia wymienione w tym artykule mogą okazać się przydatne podczas przenoszenia:</span><span class="sxs-lookup"><span data-stu-id="1036f-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="1036f-105">[Analizator przenośności .NET](../../standard/analyzers/portability-analyzer.md) — łańcucha narzędzi, który może generować raport dotyczący sposobu, w jaki przenośny kod jest między .NET Framework i .NET Core:</span><span class="sxs-lookup"><span data-stu-id="1036f-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="1036f-106">Jako [Narzędzie wiersza polecenia](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="1036f-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="1036f-107">Jako [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="1036f-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="1036f-108">[Analizator zgodności platformy](../../standard/analyzers/platform-compat-analyzer.md) — Analizator Roslyny, który informuje deweloperów, gdy używają interfejsów API specyficznych dla platformy z witryn wywołań, w których interfejs API może być niedostępny.</span><span class="sxs-lookup"><span data-stu-id="1036f-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="1036f-109">Analizator [interfejsów API platformy .NET](../../standard/analyzers/api-analyzer.md) — Roslyn, który może pomóc w wykrywaniu problemów ze zgodnością platformy w aplikacjach i bibliotekach dla wielu platform.</span><span class="sxs-lookup"><span data-stu-id="1036f-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="1036f-110">[try-Convert](https://www.nuget.org/packages/try-convert/) -narzędzie globalne platformy .NET Core, które może przekonwertować projekt lub całe rozwiązanie do zestawu .NET SDK, w tym przenieść aplikacje klasyczne do platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1036f-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="1036f-111">Nie jest to zalecane, jeśli istnieje bardziej skomplikowana kompilacja (na przykład zadania niestandardowe, obiekty docelowe lub Importy), która odrzuca wiele typów projektów niezgodnych z platformą .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1036f-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
