---
title: Składniki architektury .NET
description: Opisuje składniki architektury .NET, takie jak .NET Standard, implementacje platformy .NET, środowiska uruchomieniowe platformy .NET i narzędzia.
author: cartermp
ms.date: 10/05/2020
ms.openlocfilehash: 00d05ee328087042f7603779438436656c45be48
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819425"
---
# <a name="net-architectural-components"></a>Składniki architektury .NET

Aplikacja platformy .NET jest opracowana dla i działa w co najmniej jednej *implementacji platformy .NET*. Implementacje programu .NET obejmują .NET Framework, .NET 5 (oraz .NET Core) i mono. Istnieje Specyfikacja interfejsu API wspólna dla wielu implementacji platformy .NET, która jest nazywana .NET Standard. Ten artykuł zawiera krótkie wprowadzenie do każdego z tych koncepcji.

## <a name="net-standard"></a>.NET Standard

.NET Standard to zestaw interfejsów API, które są implementowane przez podstawową bibliotekę klas implementacji platformy .NET. Bardziej formalnie jest to specyfikacja interfejsów API platformy .NET, które składają się na jednolity zestaw kontraktów, dla których kompilujesz swój kod. Te kontrakty są implementowane w wielu implementacjach platformy .NET.

.NET Standard jest [platformą docelową](glossary.md#target-framework). Jeśli kod jest przeznaczony dla wersji .NET Standard, można go uruchomić w dowolnej implementacji platformy .NET, która obsługuje tę wersję programu .NET Standard.

.NET Standard został utworzony w celu umożliwienia przenośności w różnych implementacjach platformy .NET, ale teraz platforma .NET 5 oferuje lepszy sposób udostępniania kodu na wielu platformach i obciążeń. Aby uzyskać więcej informacji, zobacz [.NET 5 i .NET Standard](net-standard.md#net-5-and-net-standard).

## <a name="net-implementations"></a>Implementacje platformy .NET

Każda implementacja platformy .NET obejmuje następujące składniki:

- Co najmniej jedno środowisko uruchomieniowe. Przykłady: .NET Framework CLR, .NET 5 CLR.
- Biblioteka klas. Przykłady: .NET Framework podstawowa Biblioteka klas, .NET 5 podstawowa Biblioteka klas.
- Opcjonalnie co najmniej jedna struktura aplikacji. Przykłady: [ASP.NET](https://www.asp.net/), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview)i [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) są zawarte w .NET Framework i .NET 5.
- Opcjonalnie narzędzia programistyczne. Niektóre narzędzia programistyczne są współużytkowane przez wiele implementacji.

Istnieją cztery implementacje platformy .NET obsługiwane przez firmę Microsoft:

- .NET 5 (i .NET Core) i nowsze wersje
- .NET Framework
- Mono
- Platforma UWP

.NET 5 to teraz podstawowa implementacja, która jest fokusem trwającego rozwoju. Program .NET 5 jest oparty na pojedynczej bazie kodu, która obsługuje wiele platform i wiele obciążeń, takich jak aplikacje klasyczne systemu Windows i aplikacje konsolowe dla wielu platform, usługi w chmurze i witryny sieci Web.

### <a name="net-5"></a>.NET 5

.NET 5 to wieloplatformowa implementacja programu .NET, która jest przeznaczona do obsługi obciążeń serwera i chmury na dużą skalę. Obsługuje również inne obciążenia, w tym aplikacje klasyczne. Działa w systemach Windows, macOS i Linux. Implementuje .NET Standard, więc kod, który jest przeznaczony .NET Standard można uruchomić na platformie .NET 5. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview)i [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) działają na platformie .NET 5.

Więcej informacji można znaleźć w następujących zasobach:

- [Wprowadzenie do platformy .NET](../core/introduction.md)
- [Wybór między platformą .NET 5 i .NET Framework dla aplikacji serwerowych](choosing-core-framework-server.md)
- [.NET 5 i .NET Standard](net-standard.md#net-5-and-net-standard)

### <a name="net-framework"></a>.NET Framework

.NET Framework to oryginalna implementacja platformy .NET, która istniała od 2002. Wersje 4,5 i nowsze implementują .NET Standard, więc kod, który jest przeznaczony .NET Standard można uruchamiać w tych wersjach .NET Framework. Zawiera dodatkowe interfejsy API specyficzne dla systemu Windows, takie jak interfejsy API dla deweloperów aplikacji klasycznych systemu Windows z Windows Forms i WPF. .NET Framework jest zoptymalizowany do tworzenia aplikacji klasycznych systemu Windows.

Aby uzyskać więcej informacji, zobacz [przewodnik .NET Framework](../framework/index.yml).

### <a name="mono"></a>Mono

Mono to implementacja platformy .NET, która jest używana głównie w przypadku, gdy wymagane jest małe środowisko uruchomieniowe. Jest to środowisko uruchomieniowe, które umożliwia aplikacjom platformy Xamarin w systemach Android, macOS, iOS, systemu tvOS i systemu watchOS, co jest skoncentrowane głównie na małym rozmiarze. Program mono umożliwia również obsługę gier utworzonych przy użyciu aparatu Unity.

Obsługuje ona wszystkie aktualnie opublikowane wersje .NET Standard.

W przeszłości, mono zaimplementowano większy interfejs API .NET Framework i emuluje niektóre z najpopularniejszych możliwości w systemie UNIX. Jest on czasami używany do uruchamiania aplikacji .NET, które są zależne od tych funkcji w systemie UNIX.

Mono jest zazwyczaj używany z kompilatorem just-in-Time, ale również zawiera pełny statyczny kompilator (kompilacja przed czasem), która jest używana na platformach takich jak iOS.

Aby uzyskać więcej informacji, zobacz [dokumentację narzędzia mono](https://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Platforma uniwersalna systemu Windows (UWP)

PLATFORMY UWP to implementacja platformy .NET, która jest używana do tworzenia nowoczesnych aplikacji i oprogramowania systemu Windows z obsługą dotykową dla Internet rzeczy (IoT). Ma ona na celu ujednolicenie różnych typów urządzeń docelowych, w tym komputerów, tabletów, telefonów, a nawet konsoli Xbox. Usługa platformy UWP udostępnia wiele usług, takich jak scentralizowany magazyn aplikacji, środowisko wykonawcze i zestaw interfejsów API systemu Windows, które mają być używane zamiast Win32 (WinRT). Aplikacje można napisać w językach C++, C#, Visual Basic i JavaScript.

Aby uzyskać więcej informacji, zobacz [wprowadzenie do platforma uniwersalna systemu Windows](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>Środowiska uruchomieniowe platformy .NET

Środowisko uruchomieniowe jest środowiskiem wykonywania programu zarządzanego. System operacyjny jest częścią środowiska uruchomieniowego, ale nie należy do środowiska uruchomieniowego .NET. Poniżej przedstawiono kilka przykładów środowiska uruchomieniowego platformy .NET:

- Środowisko uruchomieniowe języka wspólnego (CLR) dla .NET Framework
- Środowisko uruchomieniowe języka wspólnego (CLR) dla platformy .NET 5
- .NET Native platforma uniwersalna systemu Windows
- Środowisko uruchomieniowe mono dla platformy Xamarin. iOS, Xamarin. Android, Xamarin. Mac i programu mono Desktop

## <a name="net-tooling-and-common-infrastructure"></a>Narzędzia .NET i wspólna infrastruktura

Masz dostęp do obszernego zestawu narzędzi i składników infrastruktury, które współpracują z każdą implementacją platformy .NET. Te narzędzia i składniki obejmują:

- Języki .NET i ich kompilatory
- System projektu .NET (oparty na plikach *. csproj*, *. vbproj* i *. fsproj* )
- [MSBuild](/visualstudio/msbuild/msbuild), aparat kompilacji używany do kompilowania projektów
- Pakiet [NuGet](/nuget/), Menedżer pakietów firmy Microsoft dla platformy .NET
- Narzędzia aranżacji kompilacji typu open source, takie jak [ciastka](https://cakebuild.net/) i [fałszywe](https://fake.build/)

Aby uzyskać więcej informacji, zobacz [Narzędzia i produktywność](../core/introduction.md#tools-and-productivity).

## <a name="applicable-standards"></a>Odpowiednie standardy

Specyfikacje języka C# i Common Language Infrastructure (CLI) są znormalizowane przez [Ecma International &reg; ](https://www.ecma-international.org/). Pierwsze wersje tych standardów zostały opublikowane przez ECMA w grudniu 2001.

Kolejne zmiany w standardach zostały opracowane przez grupy zadań TC49-TG2 (C#) i TC49-TG3 (CLI) w ramach języka programowania ([TC49](https://www.ecma-international.org/memento/tc49.htm)), a następnie przez proces Fast-Track ISO/IEC JTC 1 za pośrednictwem tego procesu.

### <a name="latest-standards"></a>Najnowsze standardy

Następujące oficjalne dokumenty ECMA są dostępne dla [języka C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) i [interfejsu wiersza polecenia](http://www.ecma-international.org/publications/standards/Ecma-335.htm) ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)):

- **Standard języka C# (wersja 5,0)**: [ECMA-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **Common Language Infrastructure**: dostępne w formacie [PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf) i w postaci [zip](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip) .
- **Informacje pochodzące z pliku XML partycji IV**: dostępne w formatach [PDF](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf) i [zip](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip) .

Oficjalne dokumenty ISO/IEC są dostępne na stronie [standardy dostępne publicznie](https://standards.iso.org/ittf/PubliclyAvailableStandards/) ISO/IEC. Te linki są bezpośrednie ze strony:

- **Information Technology — Języki programowania — C#**: [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Technologia informacyjna — Common Language Infrastructure (CLI) partycje I do VI**: [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Technologia informacyjna — Common Language Infrastructure (CLI) — raport techniczny dotyczący informacji pochodnych z pliku XML partycji IV**: [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>Zobacz także

- [Wprowadzenie do platformy .NET](../core/introduction.md)
- [.NET Standard wprowadzenie](net-standard.md)
- [Wybór między platformą .NET 5 i .NET Framework dla aplikacji serwerowych](choosing-core-framework-server.md)
- [Przewodnik programu .NET Framework](../framework/index.yml)
- [Przewodnik języka C#](../csharp/index.yml)
- [Przewodnik języka F#](../fsharp/index.yml)
- [Przewodnik języka Visual Basic](../visual-basic/index.yml)
