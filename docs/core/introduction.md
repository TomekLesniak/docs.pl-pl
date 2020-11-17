---
title: Wprowadzenie i Omówienie platformy .NET
description: Dowiedz się więcej na temat platformy .NET, bezpłatnej platformy deweloperskiej typu open source do tworzenia wielu rodzajów aplikacji.
author: tdykstra
ms.date: 11/16/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 1fd452ac9b7740c428e92cc6a510bab5f4d2d7d0
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687520"
---
# <a name="introduction-to-net"></a>Wprowadzenie do platformy .NET

.NET to bezpłatna platforma programistyczna typu open source do tworzenia wielu rodzajów aplikacji, takich jak:

* [Aplikacje sieci Web, interfejsy API sieci Web i mikrousługi](/aspnet/core/introduction-to-aspnet-core#recommended-learning-path)
* [Funkcje bezserwerowe w chmurze](/azure/azure-functions/functions-create-first-function-vs-code?pivots=programming-language-csharp)
* [Aplikacje natywne dla chmury](../architecture/cloud-native/index.md)
* [Aplikacje mobilne](https://dotnet.microsoft.com/learn/xamarin/hello-world-tutorial/intro)
* Aplikacje klasyczne
  * [WPF systemu Windows](/dotnet/desktop/wpf/)
  * [Windows Forms](/dotnet/desktop/winforms/)
  * [Platforma uniwersalna systemu Windows (UWP)](/windows/uwp/get-started/create-a-hello-world-app-xaml-universal)
* [Zainstalowane](https://dotnet.microsoft.com/apps/games)
* [Internet rzeczy (IoT)](/dotnet/iot)
* [Uczenie maszynowe](../machine-learning/index.yml)
* [Aplikacje konsolowe](tutorials/with-visual-studio-code.md)
* [Usługi systemu Windows](/aspnet/core/host-and-deploy/windows-service)

Udostępnianie funkcji między różnymi aplikacjami i typami aplikacji za pomocą [bibliotek klas](../standard/class-libraries.md).

Przy użyciu platformy .NET kod i pliki projektu wyglądają i działają tak samo niezależnie od typu aplikacji, która jest tworzona. Masz dostęp do tych samych funkcji środowiska uruchomieniowego, interfejsu API i języka dla każdej aplikacji.

## <a name="cross-platform"></a>Wiele platform

Możesz tworzyć aplikacje .NET dla wielu systemów operacyjnych, w tym:

* Windows
* macOS
* Linux
* Android
* iOS
* tvOS
* watchOS

Obsługiwane architektury procesora obejmują:

* x64
* x86
* ARM32
* ARM64

Platforma .NET umożliwia korzystanie z funkcji specyficznych dla platformy, takich jak interfejsy API systemu operacyjnego. Przykłady to Windows Forms i WPF w systemie Windows oraz natywne powiązania z każdą platformą mobilną z platformy Xamarin.

Aby uzyskać więcej informacji, zobacz temat [obsługiwane zasady cyklu życia systemu operacyjnego](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) i [Katalog programu .NET RID](rid-catalog.md).

## <a name="open-source"></a>Technologia open source

.NET to środowisko Open Source korzystające z [licencji MIT i Apache 2](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT). .NET jest projektem [platformy .NET Foundation](https://dotnetfoundation.org/).

Aby uzyskać więcej informacji, zobacz [listę repozytoriów projektu w witrynie GitHub.com](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Pomoc techniczna

Platforma .NET jest obsługiwana przez firmę Microsoft w systemach Windows, macOS i Linux. Jest ona regularnie aktualizowana pod kątem bezpieczeństwa i jakości, w drugi wtorek każdego miesiąca.

Dystrybucje binarne platformy .NET od firmy Microsoft zostały skompilowane i przetestowane na serwerach obsługiwanych przez firmę Microsoft na platformie Azure i postępować zgodnie z zasadami inżynierii i zabezpieczeń firmy Microsoft.

[Red Hat obsługuje platformę .NET](https://developers.redhat.com/topics/dotnet/) na Red Hat Enterprise Linux (RHEL). Red Hat i Microsoft Współpracuj, aby upewnić się, że .NET Core działa dobrze na RHEL.

[Tizen obsługuje](https://developer.tizen.org/development/training/.net-application) platformę .NET na platformach Tizen.

Aby uzyskać więcej informacji, zobacz [wersje i obsługa oprogramowania .NET Core i .NET 5](releases-and-support.md).

## <a name="tools-and-productivity"></a>Narzędzia i produktywność

Platforma .NET udostępnia wybór języków, zintegrowanych środowisk programistycznych (środowisk IDE) i innych narzędzi.

### <a name="programming-languages"></a>Języki programowania

Platforma .NET obsługuje trzy języki programowania:

* [C#](../csharp/index.yml)

  C# ("Zobacz Sharp") to nowoczesny, zorientowany obiektowo i bezpieczny dla typu język programowania. Język C# ma swoje elementy główne w rodzinie C i będzie od razu zaznajomiony z programistami C, C++, Java i JavaScript.

* [F#](../fsharp/index.yml)

  Język F # obsługuje funkcjonalne, zorientowane obiektowo i bezwzględne modele programowania.

* [Visual Basic](../visual-basic/index.yml)

  W językach .NET składnia Visual Basic jest najbardziej zbliżona do zwykłego języka ludzkiego, co może ułatwić naukę. W przeciwieństwie do języków C# i F #, dla których firma Microsoft aktywnie opracowuje nowe funkcje, język Visual Basic jest stabilny. Visual Basic nie jest obsługiwana w przypadku aplikacji sieci Web, ale jest obsługiwana przez interfejsy API sieci Web.

Poniżej przedstawiono niektóre możliwości obsługiwane przez Języki .NET:

* [Bezpieczeństwo typów](../standard/base-types/common-type-system.md)
* Wnioskowanie o typie — [C#](../csharp/programming-guide/types/index.md#specifying-types-in-variable-declarations), [F #](../fsharp/language-reference/type-inference.md), [Visual Basic](../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
* [Typy ogólne](../standard/generics.md)
* [Delegaci](../standard/delegates-lambdas.md)
* [Wyrażeń lambda](../standard/delegates-lambdas.md)
* [Zdarzenia](../standard/events/index.md)
* [Wyjątki](../standard/exceptions/index.md)
* [Atrybuty](../standard/attributes/index.md)
* [Kod asynchroniczny](../standard/async.md)
* [Programowanie równoległe](../standard/parallel-programming/index.md)
* [Analizatory kodu](../fundamentals/code-analysis/overview.md)

### <a name="ides"></a>Środowiska IDE

Zintegrowane środowiska programistyczne dla platformy .NET obejmują:

* [Visual Studio](https://visualstudio.microsoft.com/vs/)

  Działa tylko w systemie Windows. Program udostępnia wiele wbudowanych funkcji przeznaczonych do pracy z platformą .NET. Wersja Community jest bezpłatna dla studentów, współtwórców oprogramowania Open-Source i użytkowników indywidualnych.

* [Visual Studio Code](https://code.visualstudio.com/)

  Działa w systemach Windows, macOS i Linux. Bezpłatna i open source. Rozszerzenia są dostępne do pracy z językami .NET.

* [Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com/vs/mac/)

  Działa tylko na macOS. Do tworzenia aplikacji i gier .NET dla systemów iOS, Android i Web.

* [GitHub Codespaces](https://github.com/features/codespaces)

  Środowisko Visual Studio Code online, obecnie w wersji beta.

### <a name="sdk-and-runtimes"></a>Zestaw SDK i środowiska uruchomieniowe

Zestaw [SDK platformy .NET](sdk.md) to zestaw bibliotek i narzędzi służących do tworzenia i uruchamiania aplikacji platformy .NET.

Podczas [pobierania programu .NET](https://dotnet.microsoft.com/download/dotnet-core/)można wybrać zestaw SDK lub *środowisko uruchomieniowe*, takie jak środowisko uruchomieniowe platformy .NET lub środowisko uruchomieniowe ASP.NET Core. Zainstaluj środowisko uruchomieniowe na maszynie, która ma zostać przygotowana do uruchamiania aplikacji .NET. Zainstaluj zestaw SDK na komputerze, który ma być używany do programowania. Pobranie zestawu SDK powoduje automatyczne pobranie środowiska uruchomieniowego.

Pobranie zestawu SDK obejmuje następujące składniki:

* [Interfejs wiersza polecenia platformy .NET](tools/index.md). Narzędzia wiersza polecenia, których można używać do tworzenia lokalnych skryptów deweloperskich i ciągłej integracji.
* `dotnet` [Sterownik](tools/index.md#driver). Polecenie interfejsu wiersza polecenia, które uruchamia aplikacje zależne od platformy.
* Kompilatory języka programowania [Roslyn](https://github.com/dotnet/roslyn) i [F #](https://github.com/microsoft/visualfsharp) .
* Aparat kompilacji [MSBuild](/visualstudio/msbuild/msbuild) .
* [Środowisko uruchomieniowe platformy .NET](#clr). Zapewnia system typów, ładowanie zestawu, Moduł wyrzucania elementów bezużytecznych, natywną międzyoperacyjność i inne podstawowe usługi.
* [Biblioteki środowiska uruchomieniowego](#runtime-libraries). Dostarcza pierwotne typy danych i podstawowe narzędzia.
* Środowisko uruchomieniowe ASP.NET Core. Zapewnia podstawowe usługi dla aplikacji połączonych z Internetem, takich jak aplikacje internetowe, aplikacje IoT i frontony mobilne.
* Środowisko uruchomieniowe programu Desktop. Program udostępnia podstawowe usługi dla aplikacji klasycznych systemu Windows, w tym Windows Forms i WPF.

Więcej informacji można znaleźć w następujących zasobach:

* [Omówienie zestawu SDK platformy .NET](sdk.md)
* [Interfejs wiersza polecenia platformy .NET — Omówienie](tools/index.md)
* [dotnet — polecenie](tools/dotnet.md)

### <a name="project-system-and-msbuild"></a>System projektu i MSBuild

Aplikacja platformy .NET została skompilowana z kodu źródłowego przy użyciu programu [MSBuild](/visualstudio/msbuild/msbuild). Plik projektu (*. csproj*, *. fsproj* lub *. vbproj*) określa [elementy docelowe](/visualstudio/msbuild/msbuild-targets) i powiązane [zadania](/visualstudio/msbuild/msbuild-tasks) , które są odpowiedzialne za kompilowanie, pakowanie i publikowanie kodu. Istnieją identyfikatory zestawu SDK odwołujące się do standardowych kolekcji obiektów docelowych i zadań. Użycie tych identyfikatorów ułatwia przechowywanie plików projektów w małych i łatwych działaniach. Na przykład Oto plik projektu dla aplikacji konsolowej:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

A oto jeden dla aplikacji sieci Web:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

W tych przykładach `Sdk` atrybut `Project` elementu określa zestaw obiektów docelowych programu MSBuild i zadań, które kompilują projekt.  `TargetFramework`Element określa wersję platformy .NET, od której zależy aplikacja. Można edytować plik projektu w celu dodania dodatkowych obiektów docelowych i zadań specyficznych dla projektu.

Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK programu .NET](project-sdk/overview.md) i [Platformy docelowe](../standard/frameworks.md).

### <a name="cicd"></a>CI/CD

Program MSBuild i interfejs wiersza polecenia platformy .NET mogą być używane z różnymi narzędziami ciągłego integracji i środowiskami, takimi jak:

* [Funkcja GitHub Actions](https://github.com/features/actions)
* [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops)
* [CIASTK](https://cakebuild.net/)
* [SZTUCZNE](https://fake.build/)

Aby uzyskać więcej informacji, zobacz [Korzystanie z zestawu .NET SDK i narzędzi w ciągłej integracji (ci)](tools/using-ci-with-cli.md)

### <a name="nuget"></a>NuGet

[NuGet](/nuget/what-is-nuget) to Menedżer pakietów Open Source zaprojektowany dla platformy .NET. Pakiet NuGet to plik *. zip* z `.nupkg` rozszerzeniem, które zawiera skompilowany kod (dll), inne pliki związane z tym kodem oraz manifest opisowy, który zawiera informacje, takie jak numer wersji pakietu. Deweloperzy z kodem do udostępniania tworzenia pakietów i publikowania ich na [NuGet.org](https://nuget.org) lub hoście prywatnym. Deweloperzy, którzy chcą korzystać z udostępnionego kodu, dodają pakiet do projektu i mogą następnie wywołać interfejs API uwidoczniony przez pakiet w ich kodzie projektu.

Aby uzyskać więcej informacji, zobacz [dokumentację programu NuGet](/nuget/).

### <a name="net-interactive"></a>.NET Interactive

.NET Interactive to grupa narzędzi interfejsu wiersza polecenia i interfejsów API, które umożliwiają użytkownikom tworzenie interaktywnych środowisk w sieci Web, w promocji i w notesach.

Więcej informacji można znaleźć w następujących zasobach:

* [Samouczek platformy .NET In-Browser](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)
* [Korzystanie z notesów platformy .NET z programem Jupyter na maszynie](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)
* [Dokumentacja programu .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md)

## <a name="execution-models"></a>Modele wykonywania

Aplikacje platformy .NET uruchamiają [kod zarządzany](../standard/managed-code.md) w środowisku uruchomieniowym znanym jako środowisko uruchomieniowe języka wspólnego (CLR).

### <a name="clr"></a>CLR

.NET [CLR](../standard/clr.md) to Międzyplatformowy środowisko uruchomieniowe, które obejmuje obsługę systemów Windows, MacOS i Linux. Środowisko CLR obsługuje alokacje pamięci i zarządzanie nimi. Środowisko CLR jest również maszyną wirtualną, która nie tylko wykonuje aplikacje, ale również generuje i kompiluje kod przy użyciu kompilatora just-in-Time (JIT).

Aby uzyskać więcej informacji, zobacz [Omówienie środowiska uruchomieniowego języka wspólnego (CLR)](../standard/clr.md).

### <a name="jit-compiler-and-il"></a>Kompilator JIT i IL

Języki platformy .NET wyższego poziomu, takie jak C#, Kompiluj w dół do zestawu instrukcji niezależny od sprzętu, który jest nazywany językiem pośrednim (IL). Po uruchomieniu aplikacji kompilator JIT tłumaczy IL na kod maszynowy, który jest rozpoznawany przez procesor. Kompilacja JIT odbywa się na tym samym komputerze, na którym uruchomiono kod.

Ponieważ kompilacja JIT odbywa się podczas wykonywania aplikacji, czas kompilacji jest częścią czasu wykonywania. W związku z tym kompilatory JIT muszą zrównoważyć czas spędzony na optymalizowaniu kodu przed oszczędnościami, które może wygenerować ten kod. Jednak kompilator JIT wie rzeczywisty sprzęt i może zwolnić deweloperów, którzy muszą dostarczać różne implementacje dla różnych platform.

Kompilator .NET JIT może przeprowadzić *kompilację warstwową*, co oznacza, że może ponownie kompilować poszczególne metody w czasie wykonywania. Ta funkcja umożliwia szybkie Kompilowanie jej przy jednoczesnym wykorzystaniu wysoce dostrojonej wersji kodu dla często używanych metod.

Aby uzyskać więcej informacji, zobacz [proces wykonywania zarządzanego](../standard/managed-execution-process.md) i [kompilacja warstwowa](whats-new/dotnet-core-3-0.md#tiered-compilation).

### <a name="aot-compiler"></a>Kompilator AOT

Domyślne środowisko dla większości obciążeń .NET to kompilator JIT, ale platforma .NET oferuje dwie formy kompilacji z wyprzedzeniem (AOT):

* Niektóre scenariusze wymagają kompilacji na 100% AOT. Przykładem jest system [iOS](/xamarin/ios/).
* W innych scenariuszach większość kodu aplikacji jest skompilowana w drzewie AOT, ale niektóre są kompilowane w trybie JIT. Niektóre wzorce kodu nie są przyjazne dla drzewa obiektów aplikacji (takich jak generyczne). Przykładem tej formy kompilacji AOT jest [gotowy do uruchomienia](whats-new/dotnet-core-3-0.md#readytorun-images) opcja publikowania. Ta forma drzewa AOT oferuje korzyści wynikające z używania drzewa obiektów aplikacji (AOT) bez jego wad.

### <a name="automatic-memory-management"></a>Automatyczne zarządzanie pamięcią

*Moduł wyrzucania elementów bezużytecznych* zarządza alokacją i zwalnianiem pamięci dla aplikacji. Za każdym razem, gdy kod tworzy nowy obiekt, środowisko CLR przydziela pamięć dla obiektu z [zarządzanego sterty](../standard/garbage-collection/fundamentals.md#the-managed-heap). Tak długo, jak przestrzeń adresowa jest dostępna w zarządzanym stosie, środowisko wykonawcze w dalszym ciągu przydziela miejsce dla nowych obiektów. Gdy nie ma wystarczającej ilości wolnej przestrzeni adresowej, wykaz globalny sprawdza obiekty w zarządzanym stosie, które nie są już używane przez aplikację. Następnie ponownie przejmuje tę pamięć.

Wykaz globalny jest jednym z usług CLR, które pomagają zapewnić *bezpieczeństwo pamięci*. Program jest bezpieczny dla pamięci, jeśli uzyskuje dostęp tylko do przydzieloną pamięci. Na przykład środowisko uruchomieniowe zapewnia, że aplikacja nie uzyskuje dostępu do nieprzypisanej pamięci poza granicami tablicy.

Aby uzyskać więcej informacji, zobacz [Automatyczne zarządzanie pamięcią](../standard/automatic-memory-management.md) i [podstawowe informacje o wyrzucaniu elementów bezużytecznych](../standard/garbage-collection/fundamentals.md).

### <a name="working-with-unmanaged-resources"></a>Praca z niezarządzanymi zasobami

Czasami kod musi odwoływać się do *niezarządzanych zasobów*. Zasoby niezarządzane to zasoby, które nie są automatycznie obsługiwane przez środowisko uruchomieniowe platformy .NET. Na przykład dojście do pliku jest zasobem niezarządzanym. <xref:System.IO.FileStream>Obiekt jest obiektem zarządzanym, ale odwołuje się do dojścia do pliku, który jest niezarządzany. Gdy skończysz korzystać z programu <xref:System.IO.FileStream> , musisz jawnie zwolnić dojście do pliku.

W programie .NET obiekty, które odwołują się do zasobów niezarządzanych, implementują <xref:System.IDisposable> interfejs. Gdy skończysz korzystać z obiektu, wywołasz <xref:System.IDisposable.Dispose> metodę obiektu, która jest odpowiedzialna za zwolnienie niezarządzanych zasobów. Języki .NET udostępniają wygodną `using` instrukcję ([C#](../csharp/language-reference/keywords/using.md), [F #](../fsharp/language-reference/resource-management-the-use-keyword.md), [VB](../visual-basic/language-reference/statements/using-statement.md)), która zapewnia `Dispose` wywoływanie metody.

Aby uzyskać więcej informacji, zobacz [Oczyszczanie zasobów niezarządzanych](../standard/garbage-collection/unmanaged.md).

## <a name="deployment-models"></a>Modele wdrażania

Aplikacje .NET można publikować w dwóch różnych trybach:

* Opublikowanie aplikacji jako *samodzielnego* powoduje utworzenie pliku wykonywalnego, który obejmuje [środowisko uruchomieniowe](#sdk-and-runtimes) i [biblioteki](#runtime-libraries)platformy .NET oraz aplikację i jej zależności. Użytkownicy aplikacji mogą uruchomić ją na komputerze, na którym nie zainstalowano środowiska uruchomieniowego .NET. Aplikacje samodzielne są zależne od platformy i opcjonalnie można je opublikować przy użyciu formy kompilacji w [drzewie AOT](#aot-compiler).

* Publikowanie aplikacji jako *zależnej od struktury* powoduje utworzenie pliku wykonywalnego i plików binarnych (plików *dll* ), które zawierają tylko samą aplikację i jej zależności. Użytkownicy aplikacji muszą oddzielnie zainstalować [środowisko uruchomieniowe](#sdk-and-runtimes)platformy .NET. Plik wykonywalny jest specyficzny dla platformy, ale pliki *. dll* aplikacji zależnych od platformy są dla wielu platform.

  Możesz zainstalować wiele wersji środowiska uruchomieniowego obok siebie, aby uruchamiać aplikacje zależne od platformy, które są przeznaczone dla różnych wersji środowiska uruchomieniowego. Aby uzyskać więcej informacji, zobacz [Platformy docelowe](../standard/frameworks.md).

Pliki wykonywalne są tworzone dla określonych platform docelowych, które można określić za pomocą [identyfikatora czasu wykonywania (RID)](rid-catalog.md).

Aby uzyskać więcej informacji, zobacz [Omówienie publikowania aplikacji .NET](deploying/index.md) i [wprowadzenie do oprogramowania .NET i Docker](docker/introduction.md).

## <a name="runtime-libraries"></a>Biblioteki środowiska uruchomieniowego

Platforma .NET ma standardowy zestaw klas rozległych, znane jako [biblioteki środowiska uruchomieniowego](../standard/glossary.md#runtime), [biblioteki struktury](../standard/glossary.md#framework-libraries)lub [Biblioteka klas bazowych (BCL)](../standard/glossary.md#bcl). Te biblioteki zapewniają implementacje dla wielu typów i funkcji związanych z ogólnym obciążeniem.

Poniżej przedstawiono kilka przykładów typów zdefiniowanych w bibliotekach środowiska uruchomieniowego platformy .NET:

* Typy pierwotne, takie jak <xref:System.Boolean?displayProperty=nameWithType> i <xref:System.Int32?displayProperty=nameWithType> .
* Kolekcje, takie jak <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> i <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> .
* Typy danych, takie jak <xref:System.Data.DataSet?displayProperty=nameWithType> i <xref:System.Data.DataTable?displayProperty=nameWithType> .
* Typy narzędzi sieciowych, takich jak <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> .
* Typy narzędzi [we/wy plików i strumienia](../standard/io/index.md) , takie jak <xref:System.IO.FileStream?displayProperty=nameWithType> i <xref:System.IO.TextWriter?displayProperty=nameWithType> .
* Typy narzędzi [serializacji](../standard/serialization/index.md) , takie jak <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> i <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> .
* Typy wysokiej wydajności, takie jak <xref:System.Span%601?displayProperty=nameWithType> , <xref:System.Numerics.Vector?displayProperty=nameWithType> i [potoki](../standard/io/pipelines.md).

Aby uzyskać więcej informacji, zobacz [Omówienie bibliotek środowiska uruchomieniowego](../standard/runtime-libraries-overview.md). Kod źródłowy bibliotek znajduje się w [repozytorium dotnet/środowisko uruchomieniowe usługi GitHub](https://github.com/dotnet/runtime/tree/master/src/libraries).

### <a name="extensions-to-the-runtime-libraries"></a>Rozszerzenia bibliotek środowiska uruchomieniowego

Biblioteki niektórych najczęściej używanych funkcji aplikacji nie są uwzględnione w bibliotekach środowiska uruchomieniowego, ale są udostępniane w pakietach NuGet, takich jak:

| Pakiet NuGet | Dokumentacja |
|---------|---------|
| [Microsoft. Extensions. hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) | [Zarządzanie okresem istnienia aplikacji (host ogólny)](extensions/generic-host.md) |
| [Microsoft. Extensions. DependencyInjection](https://www.nuget.org/packages/Microsoft.Extensions.DependencyInjection) | [Iniekcja zależności (DI)](extensions/dependency-injection.md)
| [Microsoft.Extensions.Configwersja](https://www.nuget.org/packages/Microsoft.Extensions.Configuration) | [Konfiguracja](extensions/configuration.md) |
| [Microsoft.Extensions.Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) | [Rejestrowanie](extensions/logging.md) |
| [Microsoft. Extensions. Opcje](https://www.nuget.org/packages/Microsoft.Extensions.Options) | [Wzorzec opcji](extensions/options.md) |

Aby uzyskać więcej informacji, zobacz [repozytorium dotnet/Extensions w serwisie GitHub](https://github.com/dotnet/extensions).

## <a name="data-access"></a>Dostęp do danych

Platforma .NET udostępnia mapowanie obiekt/relacyjny (ORM) i sposób pisania zapytań SQL w kodzie.

### <a name="entity-framework-core"></a>Entity Framework Core

Entity Framework (EF) Core jest technologią dostępu do danych platformy [Open Source](https://github.com/aspnet/EntityFrameworkCore) i międzyplatformową, która może działać jako model ORM. EF Core pozwala korzystać z bazy danych, odwołując się do obiektów .NET w kodzie. Zmniejsza to ilość kodu dostępu do danych, w przeciwnym razie należy napisać i przetestować. EF Core obsługuje wiele aparatów bazy danych.

Aby uzyskać więcej informacji, zobacz [Entity Framework Core](/ef/core/) i [dostawcy bazy danych](/ef/core/providers/).

### <a name="linq"></a>LINQ

Language-Integrated Query (LINQ) umożliwia pisanie kodu deklaracyjnego do obsługi danych. Dane mogą znajdować się w wielu formularzach (takich jak obiekty znajdujące się w pamięci, bazy danych SQL lub dokumenty XML), ale kod LINQ, który jest zwykle nie różni się od źródła danych.

Aby uzyskać więcej informacji, zobacz [LINQ (Language Integrated Query) — Omówienie](../standard/linq/index.md).

## <a name="net-terminology"></a>Terminologia platformy .NET

Aby zrozumieć dokumentację platformy .NET, może pomóc wiedzieć, jak zmieniono użycie niektórych terminów w czasie.

### <a name="net-core-and-net-5"></a>.NET Core i .NET 5

W 2002 firma Microsoft udostępniła [.NET Framework](../framework/get-started/overview.md), platformę programistyczną do tworzenia aplikacji systemu Windows. Dzisiaj .NET Framework jest w wersji 4,8 i nadal jest [obsługiwane przez firmę Microsoft](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework).

W 2014 Firma Microsoft rozpoczęła pisanie następnika typu "open source" dla wielu platform, aby .NET Framework. Ta nowa implementacja programu .NET była nazywana platformą .NET Core, dopóki nie osiągnie ona wersji 3,1. Kolejna wersja programu .NET Core 3,1 to .NET 5,0, która jest obecnie dostępna w wersji zapoznawczej. Numer wersji 4 został pominięty, aby uniknąć pomyłek między tą implementacją programu .NET i .NET Framework 4,8. Nazwa "rdzeń" została porzucona, aby jasne, że jest to teraz główna implementacja platformy .NET.

Ten artykuł dotyczy platformy .NET 5, ale większość dokumentacji programu .NET 5 nadal zawiera odwołania do ".NET Core" lub ".NET Framework". Ponadto "rdzeń" pozostanie w nazwach [ASP.NET Core](/aspnet/core/) i [Entity Framework Core](/ef/core/).

Dokumentacja odnosi się również do .NET Standard. [.NET Standard](../standard/net-standard.md) to specyfikacja interfejsu API, która umożliwia tworzenie bibliotek klas dla wielu implementacji platformy .NET.

Aby uzyskać więcej informacji, zobacz [składniki architektury .NET](../standard/components.md).

### <a name="overloaded-terms"></a>Przeciążone terminy

Niektóre terminologia dla programu .NET mogą być mylące, ponieważ ten sam wyraz jest używany na różne sposoby w różnych kontekstach. Oto kilka z bardziej widocznych wystąpień:

* **środowiska uruchomieniowego**

  |Kontekst  |"środowisko uruchomieniowe" oznacza |
  |---------|---------|
  | [Środowisko uruchomieniowe języka wspólnego (CLR)](#clr)| Środowisko wykonawcze dla programu zarządzanego. System operacyjny jest częścią środowiska uruchomieniowego, ale nie należy do środowiska uruchomieniowego .NET. |
  | [Środowisko uruchomieniowe .NET na stronie pobierania platformy .NET](https://dotnet.microsoft.com/download/dotnet-core) | Biblioteki [środowiska CLR](#clr) i [środowiska uruchomieniowego](#runtime-libraries), które razem zapewniają obsługę uruchamiania aplikacji [zależnych od platformy](#deployment-models) . Strona ta oferuje również opcje środowiska uruchomieniowego dla aplikacji serwera ASP.NET Core i aplikacji klasycznych systemu Windows. |
  | [Identyfikator środowiska uruchomieniowego (RID)](rid-catalog.md) | Platforma systemu operacyjnego i architektura procesora CPU, na których działa aplikacja platformy .NET. Na przykład: Windows x64, Linux x64. |

* **Architektura**

  |Kontekst  | "struktura" oznacza |
  |---------|---------------------|
  | .NET Framework | Oryginalna implementacja programu .NET tylko dla systemu Windows. "Struktura" jest w Wielkiej litery. |
  | Platforma docelowa | Kolekcja interfejsów API, na których opiera się aplikacja lub biblioteka platformy .NET. Przykłady: .NET Core 3,1, .NET Standard 2,0 |
  | Moniker platformy docelowej (TFM)  | TFM to standardowy format tokenu służący do określania docelowej platformy aplikacji lub biblioteki platformy .NET. Przykład: `net462` dla .NET Framework 4.6.2. |
  | aplikacja zależna od struktury | Aplikacja, która może być uruchamiana tylko na komputerze, na którym zainstalowano środowisko uruchomieniowe ze [strony pobierania platformy .NET](https://dotnet.microsoft.com/download/dotnet-core). "Struktura" w tym wykorzystaniu jest taka sama jak "środowisko uruchomieniowe" pobieranej ze strony pobierania platformy .NET. |
  | biblioteki struktury | Czasami używany jako synonim dla [bibliotek środowiska uruchomieniowego](#runtime-libraries). |

* **SDK**

  |Kontekst  | "SDK" znaczenie |
  |---------|---------------|
  | [Zestaw SDK na stronie pobierania platformy .NET](#sdk-and-runtimes)  | Kolekcja narzędzi i bibliotek, które można pobrać i zainstalować, aby opracowywać i uruchamiać aplikacje platformy .NET. Obejmuje interfejs wiersza polecenia, program MSBuild, środowisko uruchomieniowe platformy .NET i inne składniki.|
  | [Projekt w stylu zestawu SDK](#project-system-and-msbuild) | Zestaw obiektów docelowych i zadań programu MSBuild, które określają sposób tworzenia projektu dla określonego typu aplikacji. Zestaw SDK w tym sensie jest określany przy użyciu `Sdk` atrybutu `Project` elementu w pliku projektu. |

* **platformach**

  |Kontekst  | "platforma" oznacza |
  |---------|--------------------|
  | wiele platform | W tym okresie "platforma" oznacza system operacyjny i sprzęt, na którym działa program, na przykład Windows, macOS, Linux, iOS i Android. |
  | Platforma .NET | Użycie jest różne. Odwołanie może dotyczyć jednej implementacji platformy .NET (na przykład .NET Framework lub .NET 5) lub do przeprowadzenia odnoszącej się koncepcji platformy .NET, w tym wszystkich implementacji. |

Aby uzyskać więcej informacji na temat terminologii .NET, zobacz [słownik platformy .NET](../standard/glossary.md).

## <a name="advanced-scenarios"></a>Scenariusze zaawansowane

W poniższych sekcjach objaśniono niektóre funkcje platformy .NET, które są przydatne w zaawansowanych scenariuszach.

### <a name="native-interop"></a>Natywna międzyoperacyjna

Każdy system operacyjny zawiera interfejs programowania aplikacji (API), który zapewnia usługi systemowe. Platforma .NET oferuje kilka sposobów wywoływania tych interfejsów API.

Głównym sposobem współpracy z natywnymi interfejsami API jest za pośrednictwem "wywołania platformy" lub P/Invoke. Metoda P/Invoke jest obsługiwana na platformach Linux i Windows. Sposób współdziałania z systemem Windows jest znany jako "międzyoperacyjność COM", która współpracuje ze [składnikami com](/cpp/atl/introduction-to-com) w kodzie zarządzanym. Jest on oparty na infrastrukturze P/Invoke, ale działa na bardzo różne sposoby.

Aby uzyskać więcej informacji, zobacz [natywne współdziałanie](../standard/native-interop/index.md).

### <a name="unsafe-code"></a>Niebezpieczny kod

W zależności od obsługi języków środowisko CLR umożliwia dostęp do pamięci natywnej i przeprowadzenie obliczeń wskaźnika za pośrednictwem `unsafe` kodu. Te operacje są niezbędne w przypadku niektórych algorytmów i współdziałania systemu. Chociaż nie jest zalecane korzystanie z niebezpiecznego kodu, chyba że jest to konieczne do współpracy z interfejsami API systemu lub implementuje najbardziej wydajny algorytm. Kod niebezpieczny może nie działać w ten sam sposób w różnych środowiskach, a także traci korzyści ze stosowania modułu wyrzucania elementów bezużytecznych i bezpieczeństwa typów. Zaleca się ograniczenie i scentralizowanie niebezpiecznego kodu, jak to możliwe, i gruntowne sprawdzenie tego kodu.

Aby uzyskać więcej informacji, zobacz artykuł [niebezpieczny kod i wskaźniki](../csharp/programming-guide/unsafe-code-pointers/index.md).

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Wybierz Samouczek platformy .NET](tutorials/index.md)

> [!div class="nextstepaction"]
> [Wypróbuj platformę .NET w przeglądarce](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

> [!div class="nextstepaction"]
> [Zapoznaj się z prezentacją języka C #](../csharp/tour-of-csharp/index.md)

> [!div class="nextstepaction"]
> [Zapoznaj się z przewodnikiem po języku F #](../fsharp/tour.md)
