---
title: Visual Studio Tools for Docker w systemie Windows
description: Poznaj narzędzia platformy Docker dostępne w programie Visual Studio 2017 w wersji 15,7 lub nowszej.
ms.date: 08/06/2020
ms.custom: vs-dotnet
ms.openlocfilehash: ae20ebf7c3c27d7f2ebe51c33719b82048f86241
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032193"
---
# <a name="use-docker-tools-in-visual-studio-on-windows"></a>Korzystanie z narzędzi platformy Docker w programie Visual Studio w systemie Windows

Przepływ pracy dla deweloperów korzystający z narzędzi platformy Docker zawartych w programie Visual Studio 2017 w wersji 15,7 lub nowszej jest podobny do używania Visual Studio Code i interfejsu wiersza polecenia platformy Docker (w rzeczywistości opiera się na tym samym interfejsie wiersza polecenia platformy Docker), ale ułatwia rozpoczęcie pracy, upraszcza proces i zapewnia większą produktywność kompilowania, uruchamiania i tworzenia zadań. Może również uruchamiać i debugować kontenery za pośrednictwem typowych `F5` `Ctrl+F5` kluczy z programu Visual Studio. Można nawet debugować całe rozwiązanie, jeśli jego kontenery są zdefiniowane w tym samym `docker-compose.yml` pliku na poziomie rozwiązania.

## <a name="configure-your-local-environment"></a>Konfigurowanie środowiska lokalnego

Najnowsze wersje Docker for Windows ułatwiają tworzenie aplikacji platformy Docker, ponieważ konfiguracja jest prosta, zgodnie z opisem w poniższych odwołaniach.

> [!TIP]
> Aby dowiedzieć się więcej o instalowaniu Docker for Windows, przejdź do ( <https://docs.docker.com/docker-for-windows/> ).

## <a name="docker-support-in-visual-studio"></a>Obsługa platformy Docker w programie Visual Studio

Istnieją dwa poziomy obsługi platformy Docker, które można dodać do projektu. W projektach ASP.NET Core można po prostu dodać `Dockerfile` plik do projektu, włączając obsługę platformy Docker. Następnym poziomem jest obsługa aranżacji kontenerów, która dodaje `Dockerfile` do projektu (jeśli jeszcze nie istnieje) i `docker-compose.yml` plik na poziomie rozwiązania. Obsługa aranżacji kontenerów za pośrednictwem Docker Compose jest domyślnie dodawana w programie Visual Studio 2017 w wersji 15,0 do 15,7. Obsługa aranżacji kontenerów to funkcja opcjonalna w programie Visual Studio 2017 w wersji 15,8 lub nowszej. Program Visual Studio 2019 lub nowszy obsługuje również wdrożenie **Kubernetes/Helm** .

Polecenia **dodaj > Docker support** i **Dodawanie > kontenerów pomocy technicznej Orchestrator** znajdują się w menu rozwijanym prawym przyciskiem myszy (lub w menu kontekstowym) węzła projektu dla projektu ASP.NET Core w **Eksplorator rozwiązań**, jak pokazano na rysunku 4-31:

![Opcja menu Dodaj obsługę platformy Docker w programie Visual Studio](media/add-docker-support-menu.png)

**Rysunek 4-31**. Dodawanie obsługi platformy Docker do projektu programu Visual Studio 2019

### <a name="add-docker-support"></a>Dodawanie obsługi platformy Docker

Oprócz opcji dodawania obsługi platformy Docker do istniejącej aplikacji, jak pokazano w poprzedniej sekcji, można również włączyć obsługę platformy Docker podczas tworzenia projektu, wybierając opcję **Włącz obsługę platformy Docker** w oknie dialogowym **Nowa aplikacja sieci Web ASP.NET Core** , które jest otwierane po kliknięciu przycisku **OK** w oknie dialogowym **nowy projekt** , jak pokazano na rysunku 4-32.

![Włącz obsługę platformy Docker dla nowej aplikacji internetowej ASP.NET Core w programie Visual Studio](media/enable-docker-support-visual-studio.png)

**Rysunek 4-32**. Włącz obsługę platformy Docker podczas tworzenia projektu w programie Visual Studio 2019

Po dodaniu lub włączeniu obsługi platformy Docker program Visual Studio dodaje do projektu plik _pliku dockerfile_ , który zawiera odwołania do wszystkich wymaganych projektów z rozwiązania.

### <a name="add-container-orchestration-support"></a>Dodawanie obsługi aranżacji kontenera

Jeśli chcesz utworzyć rozwiązanie z obsługą kilku kontenerów, Dodaj obsługę aranżacji kontenera do projektów. Dzięki temu można uruchamiać i debugować grupę kontenerów (całe rozwiązanie) w tym samym czasie, jeśli są one zdefiniowane w tym samym pliku _Docker-Compose. yml_ .

Aby dodać obsługę aranżacji kontenera, kliknij prawym przyciskiem myszy węzeł rozwiązania lub projektu w **Eksplorator rozwiązań** i wybierz polecenie **Dodaj obsługę aranżacji kontenerów >**. Następnie wybierz pozycję **Kubernetes/Helm** lub **Docker Compose** , aby zarządzać kontenerami.

Po dodaniu obsługi aranżacji kontenera do projektu zobaczysz pliku dockerfile dodaną do projektu i folderem **Docker-Zredaguj** do rozwiązania w **Eksplorator rozwiązań**, jak pokazano na rysunku 4-33:

![Pliki platformy Docker w Eksplorator rozwiązań w programie Visual Studio](media/docker-support-solution-explorer.png)

**Rysunek 4-33**. Pliki platformy Docker w Eksplorator rozwiązań w programie Visual Studio 2019

Jeśli _Docker-Compose. yml_ już istnieje, Visual Studio dodaje do niego wymagane wiersze kodu konfiguracji.

## <a name="configure-docker-tools"></a>Konfigurowanie narzędzi platformy Docker

Z menu głównego wybierz polecenie **narzędzia > opcje** i rozwiń węzeł **Narzędzia kontenera > ustawienia**. Zostaną wyświetlone ustawienia narzędzi kontenerów.

![Opcje narzędzi platformy Docker programu Visual Studio, pokazujące trzy strony: ogólne, pojedynczy projekt i Docker Compose, szczegóły w tekście artykułu.](media/visual-studio-docker-tools-options.png)

**Rysunek 4-34**. Opcje narzędzi platformy Docker

Poniższa tabela może pomóc określić, jak ustawić te opcje.

| Strona/ustawienie                                |  Ustawienie domyślne   | Opis                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------- | :----------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Strona ogólna**                            |
| Zainstaluj program Docker Desktop w razie konieczności            |     Monituj      |
| Uruchom pulpit platformy Docker w razie konieczności              |     Monituj      |
| Certyfikat SSL ASP.NET Core zaufania          |     Monituj      | Jeśli certyfikat protokołu SSL hosta lokalnego nie został oznaczony jako zaufany (z `dotnet dev-certs https --trust` ), program Visual Studio wyświetli monit za każdym razem, gdy uruchomisz projekt.                                                                                                                                                                                                                                                    |
| **Strona pojedynczego projektu**                     |
| Ściągnij wymagane obrazy platformy Docker w otwartym projekcie |        Prawda        | W celu zwiększenia wydajności podczas uruchamiania projektu program Visual Studio rozpocznie operację ściągania platformy Docker w tle, dzięki czemu gdy wszystko będzie gotowe do uruchomienia kodu, obraz jest już pobrany lub proces pobierania. Jeśli właśnie ładujesz projekty i przeglądasz kod, możesz je wyłączyć, aby uniknąć pobierania niepotrzebnych obrazów kontenerów. Może to spowolnić otwarty projekt środowiska użytkownika. |
| Ściąganie zaktualizowanych obrazów platformy Docker przy ładowaniu projektu  | Projekty .NET Core | Pobierz aktualizacje do istniejących obrazów, aby uzyskać najnowsze aktualizacje w otwartym projekcie. Może to spowolnić otwarty projekt środowiska użytkownika.                                                                                                                                                                                                                                                                                          |
| Usuń kontenery po zamknięciu projektu          |        Prawda        | Oczyść po zamknięciu projektu, co może spowolnić środowisko pracy użytkownika projektu, ale zazwyczaj jest to zwykle szybkie.                                                                                                                                                                                                                                                                                                            |
| Uruchom kontenery przy otwartym projekcie              |        Prawda        | W celu zwiększenia wydajności podczas uruchamiania projektu program Visual Studio rozpocznie pracę ze wszystkimi kontenerami w rozwiązaniu. Może to spowolnić otwarty projekt środowiska użytkownika.                                                                                                                                                                                                                                                        |
| **Docker Compose**                          |                    | Strona Docker Compose zawiera te same ustawienia co strona pojedynczego projektu, ale mają zastosowanie do rozwiązań obejmujących wiele kontenerów.                                                                                                                                                                                                                                                                                           |

> [!WARNING]
> Jeśli certyfikat protokołu SSL hosta lokalnego nie jest zaufany i ustawisz opcję na **nigdy**, żądania sieci Web HTTPS mogą kończyć się niepowodzeniem w czasie wykonywania w aplikacji lub usłudze. W takim przypadku należy ponownie ustawić wartość z powrotem, aby **monitować** lub jeszcze lepiej ufać certyfikatom na komputerze deweloperskim przy użyciu polecenia `dotnet dev-certs https --trust` .

> [!TIP]
> Aby uzyskać więcej informacji na temat implementacji usług i używania Visual Studio Tools for Docker, przeczytaj następujące artykuły:
>
> Debuguj aplikacje w lokalnym kontenerze platformy Docker: <https://docs.microsoft.com/visualstudio/containers/edit-and-refresh>
>
> Wdróż kontener ASP.NET w rejestrze kontenerów przy użyciu programu Visual Studio: <https://docs.microsoft.com/visualstudio/containers/hosting-web-apps-in-docker>

> [!div class="step-by-step"]
> [Poprzedni](docker-apps-inner-loop-workflow.md) 
>  [Dalej](set-up-windows-containers-with-powershell.md)
