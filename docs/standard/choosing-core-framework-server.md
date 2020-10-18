---
title: Wybieranie między programem .NET 5 i .NET Framework na potrzeby aplikacji serwerowych
description: Przewodnik ułatwiający podjęcie decyzji, która implementacja platformy .NET ma być używana podczas kompilowania aplikacji serwera.
author: cartermp
ms.date: 10/06/2020
ms.openlocfilehash: d9dce0343f9d37e976472b818e896a5b0a661e76
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160454"
---
# <a name="net-5-vs-net-framework-for-server-apps"></a>.NET 5 a .NET Framework dla aplikacji serwerowych

Istnieją dwa obsługiwane implementacje platformy .NET do kompilowania aplikacji po stronie serwera: .NET Framework i .NET 5 (w tym .NET Core). Obie te same składniki są współużytkowane i można udostępnić kod w obu tych samych składnikach. Istnieją jednak podstawowe różnice między tymi, a wybór zależy od tego, co chcesz osiągnąć. Ten artykuł zawiera wskazówki dotyczące tego, kiedy należy używać każdego z nich.

Użyj programu .NET 5 dla aplikacji serwera, gdy:

- Wymagania dotyczące wielu platform.
- Są one ukierunkowane na mikrousługi.
- Używasz kontenerów platformy Docker.
- Potrzebujesz wysokiej wydajności i skalowalności systemów.
- Musisz mieć obok siebie wersje platformy .NET dla każdej aplikacji.

Użyj .NET Framework dla aplikacji serwera, gdy:

- Twoja aplikacja używa obecnie .NET Framework (zalecane jest, aby zwiększyć zamiast migracji).
- Twoja aplikacja używa bibliotek .NET innych firm lub pakietów NuGet niedostępnych dla platformy .NET 5.
- Twoja aplikacja korzysta z technologii .NET, które nie są dostępne dla platformy .NET 5.
- Aplikacja korzysta z platformy, która nie obsługuje programu .NET 5.

## <a name="when-to-choose-net-5"></a>Kiedy należy wybrać platformę .NET 5

Poniższe sekcje zawierają bardziej szczegółowy opis przedstawionych wcześniej przyczyn pobrania programu .NET 5.

### <a name="cross-platform-needs"></a>Potrzeby dla wielu platform

Jeśli aplikacja (sieć Web/usługa) musi działać na wielu platformach (Windows, Linux i macOS), użyj programu .NET 5.

Platforma .NET 5 obsługuje wcześniej wymienione systemy operacyjne jako stacje robocze do tworzenia. Program Visual Studio udostępnia zintegrowane środowisko programistyczne (IDE) dla systemu Windows i macOS. Można również użyć Visual Studio Code, które działa w systemach macOS, Linux i Windows. Visual Studio Code obsługuje platformę .NET 5, w tym IntelliSense i debugowanie. Większość edytorów innych firm, takich jak subwapno, Emacs: i VI, pracują z platformą .NET 5. Te edytory innych firm uzyskują funkcję IntelliSense w edytorze przy użyciu [omnisharp](https://www.omnisharp.net/). Można również uniknąć dowolnego edytora kodu i bezpośrednio używać [interfejs wiersza polecenia platformy .NET Core](../core/tools/index.md), dostępnego dla wszystkich obsługiwanych platform.

### <a name="microservices-architecture"></a>Architektura mikrousług

Architektura mikrousług umożliwia łączenie różnych technologii między granicami usług. Ten miks technologii umożliwia stopniowe wdrażanie programu .NET 5 dla nowych mikrousług, które współpracują z innymi mikrousługami lub usługami. Można na przykład mieszać mikrousługi lub usługi opracowane za pomocą .NET Framework, Java, Ruby lub innych, monolitycznych technologii.

Dostępnych jest wiele platform infrastruktury. [Usługa Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) jest przeznaczona dla dużych i złożonych systemów mikrousług. [Azure App Service](https://azure.microsoft.com/services/app-service/) to dobry wybór w przypadku mikrousług bezstanowych. Alternatywy mikrousług oparte na platformie Docker pasują do dowolnego rodzaju podejścia mikrousług, jak wyjaśniono w sekcji [Containers](#containers) . Wszystkie te platformy obsługują platformę .NET 5 i sprawiają, że są one idealne do obsługi mikrousług.

Aby uzyskać więcej informacji o architekturze mikrousług, zobacz [.NET mikrousługi. Architektura dla kontenerów aplikacji .NET](../architecture/microservices/index.md).

### <a name="containers"></a>Kontenery

Kontenery są często używane w połączeniu z architekturą mikrousług. Kontenery mogą być również używane do konteneryzowanie aplikacji lub usług sieci Web, które są zgodne ze wzorcem architektury. .NET Framework można używać w kontenerach systemu Windows, ale modularność i lekki charakter platformy .NET 5 ułatwiają wybór dla kontenerów. Podczas tworzenia i wdrażania kontenera rozmiar jego obrazu jest znacznie mniejszy w porównaniu z platformą .NET 5 niż z .NET Framework. Ponieważ jest to platforma międzyplatformowa, można wdrożyć aplikacje serwera w kontenerach platformy Docker systemu Linux, na przykład.

Kontenery platformy Docker mogą być hostowane we własnej infrastrukturze systemu Linux lub Windows lub w usłudze w chmurze, takiej jak [usługa Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/). Usługa Azure Kubernetes umożliwia zarządzanie, organizowanie i skalowanie aplikacji opartych na kontenerach w chmurze.

### <a name="high-performance-and-scalable-systems"></a>Systemy o wysokiej wydajności i skalowalności

Gdy system potrzebuje najlepszej wydajności i skalowalności, program .NET 5 i ASP.NET Core są najlepszymi opcjami. Środowisko uruchomieniowe serwera o wysokiej wydajności dla systemów Windows Server i Linux sprawia, że platforma sieci Web jest wydajnym środowiskiem [TechEmpower na testach porównawczych](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext).

Wydajność i skalowalność są szczególnie istotne w przypadku architektury mikrousług, w których mogą być uruchomione setki mikrousług. W przypadku ASP.NET Core systemy działają z znacznie mniejszą liczbą serwerów/Virtual Machines (VM). Zredukowane serwery/maszyny wirtualne oszczędzają koszty infrastruktury i hostingu.

### <a name="side-by-side-net-versions-per-application-level"></a>Obok siebie wersje .NET na poziom aplikacji

Aby zainstalować aplikacje z zależnościami w różnych wersjach programu .NET, zalecamy platformę .NET 5. Program .NET 5 obsługuje równoległą instalację różnych wersji środowiska uruchomieniowego programu .NET 5 na tym samym komputerze. Taka instalacja równoległa umożliwia korzystanie z wielu usług na tym samym serwerze, z których każda została zainstalowana w własnej wersji programu .NET 5 (lub .NET Core 2,1 lub 3,1). Zmniejsza również ryzyko i oszczędza pieniądze w przypadku uaktualnień aplikacji i operacji IT.

Instalacja równoczesna nie jest możliwa w przypadku .NET Framework. Jest to składnik systemu Windows, a w danym momencie może istnieć tylko jedna wersja. Każda wersja .NET Framework zastępuje poprzednią wersję. Jeśli zainstalujesz nową aplikację, która jest przeznaczona dla nowszej wersji .NET Framework, możesz przerwać istniejące aplikacje działające na tym komputerze, ponieważ Poprzednia wersja została zastąpiona.

## <a name="when-to-choose-net-framework"></a>Kiedy należy wybrać .NET Framework

Program .NET 5 oferuje znaczące korzyści dla nowych aplikacji i wzorców aplikacji. Jednak .NET Framework nadal jest naturalnym wyborem dla wielu istniejących scenariuszy, a w związku z tym .NET Framework nie jest zastępowana przez platformę .NET 5 dla wszystkich aplikacji serwera.

### <a name="current-net-framework-applications"></a>Bieżące .NET Framework aplikacje

W większości przypadków nie trzeba migrować istniejących aplikacji do programu .NET 5. Zamiast tego zalecane podejście polega na użyciu platformy .NET 5 podczas rozszerzając istniejącej aplikacji, takiej jak pisanie nowej usługi sieci Web w ASP.NET Core.

### <a name="third-party-libraries-or-nuget-packages-not-available-for-net-5"></a>Biblioteki innych firm lub pakiety NuGet niedostępne dla platformy .NET 5

.NET Standard umożliwia udostępnianie kodu we wszystkich implementacjach platformy .NET, w tym na platformie .NET 5. W .NET Standard 2,0, tryb zgodności umożliwia projekty .NET Standard i .NET 5 do odwoływania się do bibliotek .NET Framework. Aby uzyskać więcej informacji, zobacz [Obsługa bibliotek .NET Framework](whats-new/whats-new-in-dotnet-standard.md#support-for-net-framework-libraries).

Należy używać .NET Framework tylko w przypadkach, gdy biblioteki lub pakiety NuGet używają technologii, które nie są dostępne w .NET Standard lub .NET 5.

### <a name="net-technologies-not-available-for-net-5"></a>Technologie .NET niedostępne dla platformy .NET 5

Niektóre technologie .NET Framework nie są dostępne w programie .NET 5. Na poniższej liście przedstawiono najpopularniejsze technologie, które nie znajdują się w programie .NET 5:

- Aplikacje ASP.NET Web Forms: formularze sieci Web ASP.NET są dostępne tylko w .NET Framework. Nie można używać ASP.NET Core dla formularzy sieci Web ASP.NET.

- Aplikacje ASP.NET Web Pages: ASP.NET Web Pages nie są uwzględnione w ASP.NET Core.

- Implementacja usług WCF. Nawet jeśli istnieje [Biblioteka klienta WCF](https://github.com/dotnet/wcf) do korzystania z usług WCF z platformy .NET 5, implementacja serwera WCF jest obecnie dostępna tylko w .NET Framework.

- Usługi związane z przepływem pracy: Windows Workflow Foundation (WF), usługi Workflow Services (WCF + WF w jednej usłudze) i Usługi danych programu WCF (wcześniej znane jako "ADO.NET Data Services") są dostępne tylko w .NET Framework.

- Obsługa języków: w programie .NET 5 są obecnie obsługiwane Visual Basic i F #, ale nie dla wszystkich typów projektów. Aby zapoznać się z listą obsługiwanych szablonów projektu, zobacz [Opcje szablonu dla programu dotnet New](../core/tools/dotnet-new.md#arguments).

Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET 5](../core/porting/net-framework-tech-unavailable.md).

### <a name="platform-doesnt-support-net-5"></a>Platforma nie obsługuje programu .NET 5

Niektóre platformy firmy Microsoft lub innych firm nie obsługują platformy .NET 5. Niektóre usługi platformy Azure udostępniają zestaw SDK, który nie jest jeszcze dostępny do użycia w programie .NET 5. W takich przypadkach można użyć równoważnego interfejsu API REST zamiast zestawu SDK klienta.

## <a name="see-also"></a>Zobacz też

- [Wybierz między ASP.NET a ASP.NET Core](/aspnet/core/choose-aspnet-framework)
- [Platforma ASP.NET Core ukierunkowana na platformę .NET Framework](/aspnet/core/introduction-to-aspnet-core?view=aspnetcore-2.2&preserve-view=true#aspnet-core-targeting-net-framework)
- [Platformy docelowe](frameworks.md)
- [Wprowadzenie do platformy .NET](../core/introduction.md)
- [Przenoszenie z .NET Framework do platformy .NET 5](../core/porting/index.md)
- [Wprowadzenie do platform .NET i Docker](../core/docker/introduction.md)
- [Przegląd składników platformy .NET](components.md)
- [Mikrousługi platformy .NET. Architektura dla kontenerów aplikacji .NET](../architecture/microservices/index.md)
