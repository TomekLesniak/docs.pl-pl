---
title: Przepływ pracy wewnętrznej pętli tworzenia kodu dla aplikacji platformy Docker
description: Dowiedz się więcej o przepływie pracy programistycznej "pętla wewnętrzna" dla aplikacji platformy Docker.
ms.date: 08/06/2020
ms.openlocfilehash: d66274a64591f79f242c1e8a63951b51d94a9ecd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676533"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Przepływ pracy wewnętrznej pętli tworzenia kodu dla aplikacji platformy Docker

Przed wyzwoleniem przepływu pracy z pętlą zewnętrzną obejmującą cały cykl DevOps, wszystko to rozpocznie się na maszynie każdego dewelopera, kodowanie samej aplikacji przy użyciu preferowanych języków lub platform i przetestowanie go lokalnie (rysunek 4-21). Jednak w każdym przypadku będziesz mieć ważny, niezależnie od tego, jaki język, struktura lub platformy są wybrane. W tym konkretnym przepływie pracy są zawsze opracowywanie i testowanie kontenerów platformy Docker w innych środowiskach, ale lokalnie.

![Diagram przedstawiający koncepcję środowiska deweloperskiego pętli wewnętrznej.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

**Rysunek 4-21**. Kontekst programowania pętli wewnętrznej

Kontener lub wystąpienie obrazu platformy Docker będzie zawierać następujące składniki:

- Wybór systemu operacyjnego (na przykład dystrybucja systemu Linux lub Windows)

- Pliki dodane przez dewelopera (na przykład pliki binarne aplikacji)

- Konfiguracja (na przykład ustawienia środowiska i zależności)

- Instrukcje dotyczące procesów uruchamianych przez platformę Docker

Można skonfigurować przepływ pracy programowania w pętli wewnętrznej, który wykorzystuje platformę Docker jako proces (opisany w następnej sekcji). Należy pamiętać, że wstępne kroki konfigurowania środowiska nie są uwzględniane, ponieważ wystarczy tylko raz.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Tworzenie pojedynczej aplikacji w kontenerze platformy Docker przy użyciu Visual Studio Code i interfejsu wiersza polecenia platformy Docker

Aplikacje składają się z własnych usług i dodatkowych bibliotek (zależności).

Na rysunku 4-22 przedstawiono podstawowe kroki, które zwykle trzeba wykonać podczas kompilowania aplikacji platformy Docker, a następnie szczegółowe opisy poszczególnych kroków.

![Diagram przedstawiający siedem kroków potrzebnych do utworzenia aplikacji z kontenerem.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

**Rysunek 4-22**. Przepływ pracy wysokiego poziomu dla cyklu życia aplikacji kontenera platformy Docker przy użyciu interfejsu wiersza polecenia platformy Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Krok 1. Rozpoczynanie kodowania w Visual Studio Code i Tworzenie początkowej aplikacji/podstawy usługi

Sposób tworzenia aplikacji jest podobny do sposobu, w jaki to zrobisz, bez dokowania. Różnica polega na tym, że podczas tworzenia i testowania aplikacji lub usług działających w kontenerach platformy Docker umieszczonych w środowisku lokalnym (na przykład w przypadku maszyn wirtualnych z systemem Linux lub Windows).

**Konfigurowanie środowiska lokalnego**

Najnowsze wersje oprogramowania Docker Desktop dla komputerów Mac i systemu Windows ułatwiają tworzenie aplikacji platformy Docker, a instalacja jest prosta.

> [!TIP]
> Aby uzyskać instrukcje dotyczące konfigurowania pulpitu platformy Docker dla systemu Windows, przejdź do <https://docs.docker.com/docker-for-windows/> .
>
> Aby uzyskać instrukcje dotyczące konfigurowania pulpitu platformy Docker dla komputerów Mac, przejdź do <https://docs.docker.com/docker-for-mac/> .

Ponadto potrzebny jest Edytor kodu, dzięki czemu można w rzeczywistości opracowywać aplikację przy użyciu interfejsu wiersza polecenia platformy Docker.

Firma Microsoft udostępnia Visual Studio Code, który jest lekkim edytorem kodu obsługiwanym w systemach Windows, Linux i macOS, oraz udostępnia technologię IntelliSense z [obsługą wielu języków](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, go, Java, Ruby, Python i większość nowoczesnych języków), [debugowanie](https://code.visualstudio.com/Docs/editor/debugging), [integrację z](https://code.visualstudio.com/Docs/editor/versioncontrol) [obsługą git i rozszerzeniami](https://code.visualstudio.com/docs/extensions/overview). Ten Edytor jest doskonałym rozwiązaniem dla deweloperów systemów macOS i Linux. W systemie Windows można również użyć programu Visual Studio.

> [!TIP]
> Aby uzyskać instrukcje dotyczące instalowania Visual Studio Code dla systemu Windows, Linux lub macOS, przejdź do <https://code.visualstudio.com/docs/setup/setup-overview/> .
>
> Aby uzyskać instrukcje dotyczące konfigurowania platformy Docker dla komputerów Mac, przejdź do <https://docs.docker.com/docker-for-mac/> .

Możesz współpracować z interfejsem wiersza polecenia platformy Docker i pisać kod przy użyciu dowolnego edytora kodu, ale używanie Visual Studio Code z rozszerzeniem Docker ułatwia tworzenie i opracowywanie `Dockerfile` `docker-compose.yml` plików w obszarze roboczym. Możesz również uruchamiać zadania i skrypty z Visual Studio Code IDE, aby wykonywać polecenia platformy Docker przy użyciu interfejsu wiersza polecenia platformy Docker poniżej.

Rozszerzenie Docker dla VS Code zapewnia następujące funkcje:

- Automatyczne `Dockerfile` i `docker-compose.yml` generowanie plików

- Podświetlanie składni i wskazówki dotyczące kursora dla `docker-compose.yml` i `Dockerfile` plików

- Technologia IntelliSense (uzupełnianie) `Dockerfile` dla `docker-compose.yml` plików i

- Zaznaczanie błędów (błędy i ostrzeżenia) dla `Dockerfile` plików

- Paleta poleceń (F1) dla najpopularniejszych poleceń platformy Docker

- Integracja Eksploratora do zarządzania obrazami i kontenerami

- Wdróż obrazy z DockerHub i rejestrów kontenerów platformy Azure, aby Azure App Service

Aby zainstalować rozszerzenie platformy Docker, naciśnij kombinację klawiszy Ctrl + Shift + P, wpisz `ext install` polecenie, a następnie uruchom rozszerzenie install, aby wyświetlić listę rozszerzeń portalu Marketplace. Następnie wpisz **Docker** , aby przefiltrować wyniki, a następnie wybierz rozszerzenie obsługa platformy Docker, jak przedstawiono na rysunku 4-23.

![Widok rozszerzenia Docker dla VS Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

**Rysunek 4-23**. Instalowanie rozszerzenia platformy Docker w Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Krok 2. Tworzenie pliku dockerfile związanych z istniejącym obrazem (zwykłego systemu operacyjnego lub środowisk deweloperskich, takich jak .NET Core, Node.js i Ruby)

Musisz utworzyć `DockerFile` obraz niestandardowy do skompilowania i na kontener, który ma zostać wdrożony. Jeśli Twoja aplikacja składa się z pojedynczej usługi niestandardowej, będziesz potrzebować jednego z nich `DockerFile` . Jeśli jednak aplikacja składa się z wielu usług (podobnie jak w przypadku architektury mikrousług), będzie potrzebna jedna `Dockerfile` na usługę.

`DockerFile`Jest to zwykle umieszczane w folderze głównym aplikacji lub usługi i zawiera wymagane polecenia, dzięki czemu platforma Docker wie, jak skonfigurować i uruchomić tę aplikację lub usługę. Możesz utworzyć `DockerFile` i dodać go do projektu wraz z kodem (node.js, .NET Core itp.) lub, jeśli jesteś nowym środowiskiem, zapoznaj się z poniższą wskazówką.

> [!TIP]
> Możesz użyć rozszerzenia Docker, aby poprowadzić Cię podczas korzystania `Dockerfile` z `docker-compose.yml` plików i związanych z kontenerami platformy Docker. Na koniec prawdopodobnie napiszesz te rodzaje plików bez tego narzędzia, ale przy użyciu rozszerzenia Docker jest dobrym punktem wyjścia, który przyspiesza uczenie się.

Na rysunku 4-24 można wyświetlić kroki umożliwiające dodanie plików platformy Docker do projektu przy użyciu rozszerzenia Docker dla VS Code:

1. Otwórz paletę poleceń, wpisz "**Docker**" i wybierz pozycję "**Dodaj pliki Docker do obszaru roboczego**".
2. Wybierz platformę aplikacji (ASP.NET Core)
3. Wybierz system operacyjny (Linux)
4. Uwzględnij opcjonalne pliki Docker Compose
5. Wprowadź porty do opublikowania (80, 443)
6. Wybieranie projektu

![Kroki dodawania plików platformy Docker z rozszerzeniem platformy Docker](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

**Rysunek 4-24**. Pliki platformy Docker dodane za pomocą polecenia **Dodaj pliki platformy Docker do obszaru roboczego**

Po dodaniu pliku dockerfile należy określić, który podstawowy obraz platformy Docker będzie używany (na przykład za pomocą programu `FROM mcr.microsoft.com/dotnet/aspnet` ). Zwykle utworzysz niestandardowy obraz na podstawie obrazu podstawowego, który można uzyskać z dowolnego oficjalnego repozytorium w [rejestrze usługi Docker Hub](https://hub.docker.com/) (na przykład [obrazu dla platformy .NET Core](https://hub.docker.com/_/microsoft-dotnet/) lub [dla Node.js](https://hub.docker.com/_/node/)).

> [!TIP]
> Należy powtórzyć tę procedurę dla każdego projektu w aplikacji. Jednak rozszerzenie będzie zażądać zastąpienia wygenerowanego pliku z systemem Docker po raz pierwszy. Należy odpowiedzieć, aby nie nadpisać, dlatego rozszerzenie tworzy osobne pliki do redagowania platformy Docker, które można następnie scalić przed uruchomieniem systemu Docker — tworzenie.

**_Użyj istniejącego oficjalnego obrazu platformy Docker_**

Korzystanie z oficjalnego repozytorium stosu języka z numerem wersji zapewnia, że te same funkcje językowe są dostępne na wszystkich komputerach (w tym na etapie projektowania, testowania i produkcji).

Poniżej znajduje się przykład pliku dockerfile dla kontenera .NET Core:

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

W tym przypadku obraz jest oparty na wersji 3,1 ASP.NET Core oficjalnego obrazu platformy Docker (wiele rozwiązań dla systemów Linux i Windows), zgodnie z wierszem `FROM mcr.microsoft.com/dotnet/aspnet:3.1` . (Aby uzyskać więcej informacji na temat tego tematu, zobacz stronę [ASP.NET Core Docker](https://hub.docker.com/_/microsoft-dotnet-aspnet/) i stronę [obrazu platformy Docker programu .NET Core](https://hub.docker.com/_/microsoft-dotnet/) ).

W pliku dockerfile można także nakazać platformie Docker nasłuchiwanie portu TCP, który będzie używany w czasie wykonywania (na przykład port 80 lub 443).

Możesz określić dodatkowe ustawienia konfiguracji w pliku dockerfile, w zależności od używanego języka i platformy. Na przykład `ENTRYPOINT` wiersz z poleceniem `["dotnet", "WebMvcApplication.dll"]` instruuje platformę Docker, aby uruchomić aplikację .NET Core. Jeśli używasz zestawu SDK i interfejs wiersza polecenia platformy .NET Core ( `dotnet CLI` ) do kompilowania i uruchamiania aplikacji .NET, to ustawienie będzie inne. Kluczowym punktem jest to, że wiersz punktu wejścia i inne ustawienia zależą od języka i platformy wybranej dla aplikacji.

> [!TIP]
> Aby uzyskać więcej informacji na temat tworzenia obrazów platformy Docker dla aplikacji platformy .NET Core, przejdź do <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images> .
>
> Aby dowiedzieć się więcej na temat tworzenia własnych obrazów, przejdź do <https://docs.docker.com/engine/tutorials/dockerimages/> .

**Używanie repozytoriów obrazów wieloskładnikowych**

Nazwa pojedynczego obrazu w repozytorium może zawierać warianty platformy, takie jak obraz systemu Linux i obraz Windows. Ta funkcja umożliwia dostawcom, takim jak firma Microsoft (twórcy obrazów podstawowych), tworzenie jednego repozytorium w celu pokrycia wielu platform (to jest Linux i Windows). Na przykład repozytorium [dotnet/rdzeń/ASPNET](https://hub.docker.com/_/microsoft-dotnet-aspnet/) dostępne w rejestrze usługi Docker Hub zapewnia obsługę systemu Linux i Windows nano Server przy użyciu tej samej nazwy obrazu.

Ściąganie obrazu [dotnet/Core/ASPNET](https://hub.docker.com/_/microsoft-dotnet-aspnet/) z hosta z systemem Windows powoduje pobranie wariantu systemu Windows, podczas gdy ściąganie tej samej nazwy obrazu z hosta z systemem Linux jest ściągane.

**_Tworzenie obrazu podstawowego od podstaw_**

Możesz utworzyć własny obraz podstawowy platformy Docker od podstaw, jak wyjaśniono w tym [artykule](https://docs.docker.com/engine/userguide/eng-image/baseimages/) z platformy Docker. Ten scenariusz prawdopodobnie nie jest najlepszym rozwiązaniem, jeśli właśnie zaczynasz pracę z platformą Docker, ale jeśli chcesz ustawić określone bity obrazu podstawowego, możesz to zrobić.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Krok 3. Tworzenie niestandardowych obrazów platformy Docker osadzania w niej usługi

Dla każdej usługi niestandardowej, która składa się z aplikacji, konieczne będzie utworzenie powiązanego obrazu. Jeśli aplikacja składa się z pojedynczej usługi lub aplikacji sieci Web, będzie potrzebny tylko jeden obraz.

> [!NOTE]
> Podczas wzięcia pod uwagę "przepływu pracy DevOps pętla zewnętrzna" obrazy zostaną utworzone przez zautomatyzowany proces kompilacji po każdym wypchnięciu kodu źródłowego do repozytorium git (ciągłej integracji), dzięki czemu obrazy zostaną utworzone w tym środowisku globalnym z kodu źródłowego.
>
> Jednak przed rozważeniem przechodzenia do tej trasy z pętlą zewnętrzną należy upewnić się, że aplikacja platformy Docker rzeczywiście działa prawidłowo, aby nie wypchnięcia kodu, który może nie działać prawidłowo w systemie kontroli źródła (git itp.).
>
> W związku z tym każdy Deweloper musi najpierw wykonać cały proces pętli wewnętrznej, aby przetestować lokalnie i kontynuować programowanie do momentu, gdy chcą wypchnąć kompletną funkcję lub zmienić system kontroli źródła.

Aby utworzyć obraz w środowisku lokalnym i przy użyciu pliku dockerfile, można użyć polecenia Docker Build, jak pokazano na rysunku 4-25, ponieważ jest już Tagi obrazu dla Ciebie i tworzy obrazy dla wszystkich usług w aplikacji za pomocą prostego polecenia.

![Zrzut ekranu przedstawiający dane wyjściowe konsoli polecenia Docker-Zredaguj Build.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

**Rysunek 4-25**. Uruchamianie kompilacji platformy Docker

Opcjonalnie, zamiast bezpośrednio z `docker build` poziomu folderu projektu, można najpierw wygenerować folder do wdrożenia z bibliotekami platformy .NET wymaganymi przy użyciu `dotnet publish` polecenia Uruchom, a następnie uruchomić polecenie `docker build` .

W tym przykładzie tworzony jest obraz platformy Docker o nazwie `explore-docker-vscode/webapi:latest` ( `:latest` jest to tag, taki jak określona wersja). Ten krok można wykonać dla każdego niestandardowego obrazu, który trzeba utworzyć dla złożonej aplikacji platformy Docker z kilkoma kontenerami. Jednak w następnej sekcji zobaczymy, że jest to łatwiejsze w użyciu `docker-compose` .

Istniejące obrazy można znaleźć w lokalnym repozytorium (na komputerze deweloperskim) przy użyciu `docker images` polecenia, jak pokazano na rysunku 4-26.

![Dane wyjściowe konsoli z obrazów platformy Docker, pokazujące istniejące obrazy.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

**Rysunek 4-26**. Wyświetlanie istniejących obrazów przy użyciu obrazów platformy Docker

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Krok 4. Definiowanie usług w Docker-Compose. yml podczas tworzenia złożonej aplikacji platformy Docker z wieloma usługami

Przy użyciu `docker-compose.yml` pliku można zdefiniować zestaw powiązanych usług, które mają zostać wdrożone jako aplikacja składająca się z poleceniami wdrażania wyjaśnionymi w następnym kroku.

Utwórz ten plik w folderze głównym lub głównym rozwiązania. powinna zawierać zawartość podobną do pokazanej w tym `docker-compose.yml` pliku:

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

W tym konkretnym przypadku ten plik definiuje trzy usługi: usługę internetowego interfejsu API (usługę niestandardową), aplikację sieci Web i usługę Redis (popularne usługi pamięci podręcznej). Każda usługa zostanie wdrożona jako kontener, dlatego należy użyć konkretnego obrazu platformy Docker dla każdej z nich. Dla tej konkretnej aplikacji:

- Usługa internetowego interfejsu API została skompilowana z pliku dockerfile w `src/WebApi/Dockerfile` katalogu.

- Port 51080 hosta jest przekazywany do uwidocznionego portu 80 w `webapi` kontenerze.

- Usługa internetowego interfejsu API zależy od usługi Redis

- Aplikacja sieci Web uzyskuje dostęp do usługi internetowego interfejsu API przy użyciu adresu wewnętrznego: `http://webapi` .

- Usługa Redis używa [najnowszego publicznego obrazu Redis](https://hub.docker.com/_/redis/) pobranego z rejestru usługi Docker Hub. [Redis](https://redis.io/) to popularny system pamięci podręcznej dla aplikacji po stronie serwera.

### <a name="step-5-build-and-run-your-docker-app"></a>Krok 5. Kompilowanie i uruchamianie aplikacji platformy Docker

Jeśli aplikacja ma tylko jeden kontener, wystarczy ją uruchomić, wdrażając ją na hoście platformy Docker (maszynie wirtualnej lub serwerze fizycznym). Jeśli jednak aplikacja składa się z wielu usług, musisz _ją utworzyć_. Zobaczmy różne opcje.

**_Opcja A: uruchamianie jednego kontenera lub usługi_**

Obraz platformy Docker można uruchomić przy użyciu polecenia Docker Run, jak pokazano poniżej:

```console
docker run -t -d -p 50080:80 explore-docker-vscode/webapp:latest
```

W przypadku tego konkretnego wdrożenia będziemy przekierowywać żądania wysyłane do portu 50080 na hoście do wewnętrznego portu 80.

**_Opcja B: redagowanie i uruchamianie aplikacji z wieloma kontenerami_**

W większości scenariuszy przedsiębiorstwa aplikacja platformy Docker będzie składać się z wielu usług. W takich przypadkach można uruchomić `docker-compose up` polecenie (rysunek 4-27), które będzie używać wcześniej utworzonego pliku Docker-Compose. yml. Uruchomienie tego polecenia kompiluje wszystkie obrazy niestandardowe i wdraża aplikację złożoną ze wszystkimi powiązanymi kontenerami.

![Dane wyjściowe konsoli z platformy Docker — tworzenie.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

**Rysunek 4-27**. Wyniki uruchamiania polecenia "Docker-Zredaguj do"

Po uruchomieniu `docker-compose up` programu aplikacja i powiązane z nim kontenery są wdrażane na hoście platformy Docker, jak pokazano na rysunku 4-28 w reprezentacji maszyny wirtualnej.

![Maszyna wirtualna z uruchomioną funkcją wielokontenera aplikacji.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

**Rysunek 4-28**. Maszyna wirtualna z wdrożonymi kontenerami platformy Docker

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Krok 6. Testowanie aplikacji platformy Docker (lokalnie, na lokalnej maszynie wirtualnej z płytą CD)

Ten krok będzie się różnić w zależności od tego, co aplikacja działa.

W prostym interfejsie API sieci Web platformy .NET Core "Hello world" wdrożonym jako pojedynczy kontener lub usługa, wystarczy uzyskać dostęp do usługi, podając port TCP określony w pliku dockerfile.

Na hoście platformy Docker Otwórz przeglądarkę i przejdź do tej witryny. powinna zostać wyświetlona aplikacja/usługa, jak pokazano na rysunku 4-29.

![Widok przeglądarki odpowiedzi z localhost/API/Values.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

**Rysunek 4-29**. Lokalne testowanie aplikacji platformy Docker przy użyciu przeglądarki

Należy zauważyć, że korzysta on z portu 50080, ale wewnętrznie jest przekierowywany do portu 80, ponieważ został on wdrożony w programie `docker compose` , jak wyjaśniono wcześniej.

Można to przetestować przy użyciu przeglądarki korzystającej z wypełniania z terminalu, jak przedstawiono na rysunku 4-30.

![Uzyskano wynik zwinięcie z http://localhost:51080/WeatherForecast](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

**Rysunek 4-30**. Lokalne testowanie aplikacji platformy Docker przy użyciu programu ZWINIĘCIE

**Debugowanie kontenera działającego na platformie Docker**

Visual Studio Code obsługuje debugowanie platformy Docker, jeśli używasz Node.js i innych platform, takich jak kontenery .NET Core.

Można również debugować kontenery .NET Core lub .NET Framework w programie Docker podczas korzystania z programu Visual Studio dla systemu Windows lub Mac, zgodnie z opisem w następnej sekcji.

> [!TIP]
> Aby dowiedzieć się więcej na temat debugowania Node.js kontenerów platformy Docker, zobacz <https://blog.docker.com/2016/07/live-debugging-docker/> i <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more> .

> [!div class="step-by-step"]
> [Poprzedni](docker-apps-development-environment.md) 
>  [Dalej](visual-studio-tools-for-docker.md)
