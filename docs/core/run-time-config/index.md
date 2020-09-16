---
title: Opcje konfiguracji czasu wykonywania
description: Dowiedz się, jak skonfigurować aplikacje platformy .NET Core za pomocą ustawień konfiguracji czasu wykonywania.
ms.date: 01/21/2020
ms.openlocfilehash: 21673a221d0f21202febf4730b955da66132d5f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538201"
---
# <a name="net-core-run-time-configuration-settings"></a>Ustawienia konfiguracji środowiska uruchomieniowego .NET Core

Platforma .NET Core obsługuje używanie plików konfiguracji i zmiennych środowiskowych w celu skonfigurowania zachowania aplikacji .NET Core w czasie wykonywania. Konfiguracja czasu wykonywania jest atrakcyjną opcją, jeśli:

- Nie jesteś własnością ani nie kontrolujesz kodu źródłowego dla aplikacji, dlatego nie można programowo skonfigurować go.

- Wiele wystąpień aplikacji jest wykonywanych w tym samym czasie w pojedynczym systemie i chcesz skonfigurować każdą z nich w celu uzyskania optymalnej wydajności.

> [!NOTE]
> Ta dokumentacja jest w toku. Jeśli zauważysz, że informacje przedstawione w tym miejscu są niekompletne lub niedokładne, należy [otworzyć problem](https://github.com/dotnet/docs/issues) , aby poinformować nas o tym lub [przesłać żądanie ściągnięcia](https://github.com/dotnet/docs/pulls) w celu rozwiązania problemu. Informacje o przesyłaniu żądań ściągnięcia dla repozytorium dotnet/docs można znaleźć w [przewodniku współautora](/contribute/dotnet/dotnet-contribute).

Platforma .NET Core udostępnia następujące mechanizmy konfigurowania zachowania aplikacji w czasie wykonywania:

- [runtimeconfig.jspliku](#runtimeconfigjson)

- [właściwości programu MSBuild](#msbuild-properties)

- [Zmienne środowiskowe](#environment-variables)

> [!TIP]
> Skonfigurowanie opcji czasu wykonywania przy użyciu zmiennej środowiskowej stosuje ustawienie do wszystkich aplikacji platformy .NET Core. Skonfigurowanie opcji czasu wykonywania w pliku *runtimeconfig.js* lub projektu powoduje zastosowanie ustawienia tylko do tej aplikacji.

Niektóre wartości konfiguracji można również ustawić programowo, wywołując <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodę.

Artykuły w tej sekcji dokumentacji są zorganizowane według kategorii, na przykład [debugowania](debugging-profiling.md) i [wyrzucania elementów bezużytecznych](garbage-collector.md). Jeśli ma to zastosowanie, opcje konfiguracji są wyświetlane dla *runtimeconfig.js* plików, właściwości programu MSBuild, zmiennych środowiskowych i, w przypadku plików referencyjnych, *app.config* dla projektów .NET Framework.

## <a name="runtimeconfigjson"></a>runtimeconfig.jsna

Po [skompilowaniu](../tools/dotnet-build.md)projektu w katalogu wyjściowym zostanie wygenerowany element *[nazwa_aplikacji] .runtimeconfig.jsw* pliku. Jeśli *runtimeconfig.template.jsw* pliku istnieje w tym samym folderze co plik projektu, wszystkie opcje konfiguracji, które zawiera, zostaną scalone w *.runtimeconfig.js[nazwa_aplikacji] w* pliku. W przypadku kompilowania aplikacji należy umieścić dowolne opcje konfiguracji w *runtimeconfig.template.js* pliku. Jeśli właśnie uruchamiasz aplikację, Wstaw ją bezpośrednio do programu *[nazwa_aplikacji] .runtimeconfig.js* pliku.

> [!NOTE]
> Plik *[nazwa_aplikacji] .runtimeconfig.jsw* pliku zostanie nadpisany w kolejnych kompilacjach.

Określ opcje konfiguracji czasu wykonywania w sekcji **configProperties** *runtimeconfig.jsna* plikach. Ta sekcja ma postać:

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>Przykład [nazwa_aplikacji] .runtimeconfig.jsw pliku

Jeśli umieszczasz opcje w wyjściowym pliku JSON, zastąp je `runtimeOptions` właściwością.

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a>Przykład runtimeconfig.template.jspliku

Jeśli umieszczasz opcje w pliku JSON szablonu, Pomiń `runtimeOptions` Właściwość.

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a>właściwości programu MSBuild

Niektóre opcje konfiguracji czasu wykonywania można ustawić przy użyciu właściwości programu MSBuild w pliku *. csproj* lub *. vbproj* projektów .NET Core w stylu zestawu SDK. Właściwości programu MSBuild mają pierwszeństwo przed opcjami ustawionymi w *runtimeconfig.template.js* pliku. Zastępują one również wszystkie opcje ustawione w programie *[nazwa_aplikacji] .runtimeconfig.jsw* pliku podczas kompilacji.

Oto przykładowy plik projektu w stylu zestawu SDK z właściwościami MSBuild służący do konfigurowania zachowania w czasie wykonywania:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

Właściwości programu MSBuild służące do konfigurowania zachowania w czasie wykonywania są zanotowane w poszczególnych artykułach dla każdego obszaru, na przykład na [wyrzucaniu elementów bezużytecznych](garbage-collector.md). Są one również wymienione w sekcji [Konfiguracja czasu wykonywania](../project-sdk/msbuild-props.md#run-time-configuration-properties) w temacie Informacje o właściwościach programu MSBuild dla projektów w stylu zestawu SDK.

## <a name="environment-variables"></a>Zmienne środowiskowe

Zmienne środowiskowe mogą służyć do dostarczania niektórych informacji o konfiguracji czasu wykonywania. Skonfigurowanie opcji czasu wykonywania przy użyciu zmiennej środowiskowej stosuje ustawienie do wszystkich aplikacji platformy .NET Core. Pokrętła konfiguracji określone jako zmienne środowiskowe zwykle mają prefiks **COMPlus_**.

Zmienne środowiskowe można definiować w panelu sterowania systemu Windows, w wierszu polecenia lub programowo poprzez wywołanie <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> metody w systemach Windows i UNIX.

W poniższych przykładach pokazano, jak ustawić zmienną środowiskową w wierszu polecenia:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
