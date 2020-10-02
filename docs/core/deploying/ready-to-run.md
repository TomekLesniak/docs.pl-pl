---
title: Przegląd wdrażania ReadyToRun
description: Dowiedz się, jakie wdrożenia ReadyToRun są i dlaczego należy rozważyć użycie jej jako części publikowania aplikacji z .NET 5 i .NET Core 3,0 i nowszych.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: b4052a0c0f4ed9f6cfd273abe5ef45d018bd0ae0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654964"
---
# <a name="readytorun-compilation"></a>Kompilacja ReadyToRun

Czas uruchamiania aplikacji .NET i opóźnienia można ulepszyć, kompilując zestawy aplikacji jako ReadyToRun (R2R). R2R to forma kompilacji z wyprzedzeniem (AOT).

Pliki binarne R2R zwiększają wydajność uruchamiania przez zmniejszenie ilości pracy kompilatora, który jest potrzebny do załadowania aplikacji. Pliki binarne zawierają podobny kod natywny w porównaniu z przeznaczeniem JIT. R2R pliki binarne są jednak większe, ponieważ zawierają kod języka pośredniego (IL), który jest nadal wymagany w niektórych scenariuszach i natywną wersję tego samego kodu. R2R jest dostępna tylko w przypadku publikowania aplikacji, która jest przeznaczona dla określonych środowisk uruchomieniowych (RID), takich jak Linux x64 lub Windows x64.

Aby skompilować projekt jako ReadyToRun, aplikacja musi być opublikowana z właściwością PublishReadyToRun ustawioną na wartość true.

Istnieją dwa sposoby publikowania aplikacji jako ReadyToRun:

01. Określ flagę PublishReadyToRun bezpośrednio w poleceniu dotnet publish. Aby uzyskać szczegółowe informacje, zobacz [dotnet Publish](../tools/dotnet-publish.md) .

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. Określ właściwość w projekcie

    - Dodaj `<PublishReadyToRun>` ustawienie do projektu.

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - Opublikuj aplikację bez żadnych specjalnych parametrów.

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a>Wpływ używania funkcji ReadyToRun

Kompilacja przed czasem ma skomplikowany wpływ na wydajność aplikacji, co może być trudne do przewidywania. Ogólnie rzecz biorąc, rozmiar zestawu zostanie powiększony do wartości z przedziału od dwóch do trzech razy większych. Ten wzrost rozmiaru fizycznego pliku może zmniejszyć wydajność ładowania zestawu z dysku i zwiększyć zestaw roboczy procesu. Jednak w przypadku zwracania Liczba metod skompilowanych w czasie wykonywania jest zwykle ograniczona. Wynika to z tego, że większość aplikacji, które mają duże ilości kodu, uzyskuje korzyści z używania funkcji ReadyToRun. Aplikacje, które mają niewielkie ilości kodu, prawdopodobnie nie wystąpią znaczącej poprawy dotyczącej włączania ReadyToRun, ponieważ biblioteki środowiska uruchomieniowego platformy .NET zostały już wstępnie skompilowane z ReadyToRun.

Ulepszenia uruchamiania omówione tutaj dotyczą tylko uruchamiania aplikacji, ale również do pierwszego użycia dowolnego kodu w aplikacji. Na przykład można użyć ReadyToRun, aby zmniejszyć opóźnienie odpowiedzi pierwszego użycia internetowego interfejsu API w aplikacji ASP.NET.

### <a name="interaction-with-tiered-compilation"></a>Interakcja z kompilacją warstwową

Wygenerowane przed chwilą nie jest tak wysoce zoptymalizowany jak kod generowany przez JIT. Aby rozwiązać ten problem, kompilacja warstwowa zastępuje często używane metody ReadyToRun z metodami generowanymi przez JIT.

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a>Jak wybierany jest zestaw wstępnie skompilowanych zestawów?

Zestaw SDK kompiluje zestawy, które są dystrybuowane z aplikacją. W przypadku aplikacji samodzielnych zestaw zestawów będzie obejmował strukturę. Pliki binarne języka C++/CLI nie kwalifikują się do kompilacji ReadyToRun.

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a>Jak wybierany jest zestaw metod do wstępnej kompilacji?

Kompilator podejmie próbę wstępnego skompilowania możliwie największej liczby metod. Jednak z różnych powodów nie jest oczekiwane, że użycie funkcji ReadyToRun spowoduje uniemożliwienie wykonania JIT.

Takie przyczyny mogą obejmować, ale nie są ograniczone do:

- Użycie typów ogólnych zdefiniowanych w oddzielnych zestawach
- Współdziałanie z kodem natywnym
- Korzystanie z wewnętrznych elementów sprzętowych, których kompilator nie może udowodnić, jest bezpieczne do użycia na komputerze docelowym
- Niektóre nietypowe wzorce IL
- Dynamiczne tworzenie metod przy użyciu odbicia lub LINQ

## <a name="cross-platformarchitecture-restrictions"></a>Ograniczenia dotyczące wielu platform/architektury

W przypadku niektórych platform zestawu SDK kompilator ReadyToRun jest w stanie wykonać kompilację krzyżową dla innych platform docelowych. Obsługiwane elementy docelowe kompilacji są opisane w poniższej tabeli.

| Platforma SDK | Obsługiwane platformy docelowe |
| ------------ | --------------------------- |
| Windows x64  | Windows x86, Windows x64, Windows ARM32, Windows ARM64 |
| Windows x86  | Windows x86, Windows ARM32 |
| Linux x64    | Linux x86, Linux x64, Linux ARM32, Linux ARM64 |
| Linux ARM32  | Linux ARM32 |
| ARM64 systemu Linux  | ARM64 systemu Linux |
| macOS x64    | macOS x64 |
