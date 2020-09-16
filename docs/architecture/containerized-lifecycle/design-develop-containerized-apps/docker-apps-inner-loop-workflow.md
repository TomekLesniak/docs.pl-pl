---
title: Przepływ pracy wewnętrznej pętli tworzenia kodu dla aplikacji platformy Docker
description: Dowiedz się więcej o przepływie pracy programistycznej "pętla wewnętrzna" dla aplikacji platformy Docker.
ms.date: 08/06/2020
ms.openlocfilehash: 071e16afede91f4cfd6cbe8662fa68814ffdcdd7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539765"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="369eb-103">Przepływ pracy wewnętrznej pętli tworzenia kodu dla aplikacji platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="369eb-104">Przed wyzwoleniem przepływu pracy z pętlą zewnętrzną obejmującą cały cykl DevOps, wszystko to rozpocznie się na maszynie każdego dewelopera, kodowanie samej aplikacji przy użyciu preferowanych języków lub platform i przetestowanie go lokalnie (rysunek 4-21).</span><span class="sxs-lookup"><span data-stu-id="369eb-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="369eb-105">Jednak w każdym przypadku będziesz mieć ważny, niezależnie od tego, jaki język, struktura lub platformy są wybrane.</span><span class="sxs-lookup"><span data-stu-id="369eb-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="369eb-106">W tym konkretnym przepływie pracy są zawsze opracowywanie i testowanie kontenerów platformy Docker w innych środowiskach, ale lokalnie.</span><span class="sxs-lookup"><span data-stu-id="369eb-106">In this specific workflow, you're always developing and testing Docker containers in no other environments, but locally.</span></span>

![Diagram przedstawiający koncepcję środowiska deweloperskiego pętli wewnętrznej.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="369eb-108">**Rysunek 4-21**.</span><span class="sxs-lookup"><span data-stu-id="369eb-108">**Figure 4-21**.</span></span> <span data-ttu-id="369eb-109">Kontekst programowania pętli wewnętrznej</span><span class="sxs-lookup"><span data-stu-id="369eb-109">Inner-loop development context</span></span>

<span data-ttu-id="369eb-110">Kontener lub wystąpienie obrazu platformy Docker będzie zawierać następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="369eb-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="369eb-111">Wybór systemu operacyjnego (na przykład dystrybucja systemu Linux lub Windows)</span><span class="sxs-lookup"><span data-stu-id="369eb-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="369eb-112">Pliki dodane przez dewelopera (na przykład pliki binarne aplikacji)</span><span class="sxs-lookup"><span data-stu-id="369eb-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="369eb-113">Konfiguracja (na przykład ustawienia środowiska i zależności)</span><span class="sxs-lookup"><span data-stu-id="369eb-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="369eb-114">Instrukcje dotyczące procesów uruchamianych przez platformę Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="369eb-115">Można skonfigurować przepływ pracy programowania w pętli wewnętrznej, który wykorzystuje platformę Docker jako proces (opisany w następnej sekcji).</span><span class="sxs-lookup"><span data-stu-id="369eb-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="369eb-116">Należy pamiętać, że wstępne kroki konfigurowania środowiska nie są uwzględniane, ponieważ wystarczy tylko raz.</span><span class="sxs-lookup"><span data-stu-id="369eb-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="369eb-117">Tworzenie pojedynczej aplikacji w kontenerze platformy Docker przy użyciu Visual Studio Code i interfejsu wiersza polecenia platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="369eb-118">Aplikacje składają się z własnych usług i dodatkowych bibliotek (zależności).</span><span class="sxs-lookup"><span data-stu-id="369eb-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="369eb-119">Na rysunku 4-22 przedstawiono podstawowe kroki, które zwykle trzeba wykonać podczas kompilowania aplikacji platformy Docker, a następnie szczegółowe opisy poszczególnych kroków.</span><span class="sxs-lookup"><span data-stu-id="369eb-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Diagram przedstawiający siedem kroków potrzebnych do utworzenia aplikacji z kontenerem.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="369eb-121">**Rysunek 4-22**.</span><span class="sxs-lookup"><span data-stu-id="369eb-121">**Figure 4-22**.</span></span> <span data-ttu-id="369eb-122">Przepływ pracy wysokiego poziomu dla cyklu życia aplikacji kontenera platformy Docker przy użyciu interfejsu wiersza polecenia platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="369eb-123">Krok 1. Rozpoczynanie kodowania w Visual Studio Code i Tworzenie początkowej aplikacji/podstawy usługi</span><span class="sxs-lookup"><span data-stu-id="369eb-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="369eb-124">Sposób tworzenia aplikacji jest podobny do sposobu, w jaki to zrobisz, bez dokowania.</span><span class="sxs-lookup"><span data-stu-id="369eb-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="369eb-125">Różnica polega na tym, że podczas tworzenia i testowania aplikacji lub usług działających w kontenerach platformy Docker umieszczonych w środowisku lokalnym (na przykład w przypadku maszyn wirtualnych z systemem Linux lub Windows).</span><span class="sxs-lookup"><span data-stu-id="369eb-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="369eb-126">**Konfigurowanie środowiska lokalnego**</span><span class="sxs-lookup"><span data-stu-id="369eb-126">**Setting up your local environment**</span></span>

<span data-ttu-id="369eb-127">Najnowsze wersje oprogramowania Docker Desktop dla komputerów Mac i systemu Windows ułatwiają tworzenie aplikacji platformy Docker, a instalacja jest prosta.</span><span class="sxs-lookup"><span data-stu-id="369eb-127">With the latest versions of Docker Desktop for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="369eb-128">Aby uzyskać instrukcje dotyczące konfigurowania pulpitu platformy Docker dla systemu Windows, przejdź do <https://docs.docker.com/docker-for-windows/> .</span><span class="sxs-lookup"><span data-stu-id="369eb-128">For instructions on setting up Docker Desktop for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
> <span data-ttu-id="369eb-129">Aby uzyskać instrukcje dotyczące konfigurowania pulpitu platformy Docker dla komputerów Mac, przejdź do <https://docs.docker.com/docker-for-mac/> .</span><span class="sxs-lookup"><span data-stu-id="369eb-129">For instructions on setting up Docker Desktop for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="369eb-130">Ponadto potrzebny jest Edytor kodu, dzięki czemu można w rzeczywistości opracowywać aplikację przy użyciu interfejsu wiersza polecenia platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="369eb-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="369eb-131">Firma Microsoft udostępnia Visual Studio Code, który jest lekkim edytorem kodu obsługiwanym w systemach Windows, Linux i macOS, oraz udostępnia technologię IntelliSense z [obsługą wielu języków](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, go, Java, Ruby, Python i większość nowoczesnych języków), [debugowanie](https://code.visualstudio.com/Docs/editor/debugging), [integrację z](https://code.visualstudio.com/Docs/editor/versioncontrol) [obsługą git i rozszerzeniami](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="369eb-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="369eb-132">Ten Edytor jest doskonałym rozwiązaniem dla deweloperów systemów macOS i Linux.</span><span class="sxs-lookup"><span data-stu-id="369eb-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="369eb-133">W systemie Windows można również użyć programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="369eb-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="369eb-134">Aby uzyskać instrukcje dotyczące instalowania Visual Studio Code dla systemu Windows, Linux lub macOS, przejdź do <https://code.visualstudio.com/docs/setup/setup-overview/> .</span><span class="sxs-lookup"><span data-stu-id="369eb-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="369eb-135">Aby uzyskać instrukcje dotyczące konfigurowania platformy Docker dla komputerów Mac, przejdź do <https://docs.docker.com/docker-for-mac/> .</span><span class="sxs-lookup"><span data-stu-id="369eb-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="369eb-136">Możesz współpracować z interfejsem wiersza polecenia platformy Docker i pisać kod przy użyciu dowolnego edytora kodu, ale używanie Visual Studio Code z rozszerzeniem Docker ułatwia tworzenie i opracowywanie `Dockerfile` `docker-compose.yml` plików w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="369eb-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="369eb-137">Możesz również uruchamiać zadania i skrypty z Visual Studio Code IDE, aby wykonywać polecenia platformy Docker przy użyciu interfejsu wiersza polecenia platformy Docker poniżej.</span><span class="sxs-lookup"><span data-stu-id="369eb-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="369eb-138">Rozszerzenie Docker dla VS Code zapewnia następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="369eb-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="369eb-139">Automatyczne `Dockerfile` i `docker-compose.yml` generowanie plików</span><span class="sxs-lookup"><span data-stu-id="369eb-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="369eb-140">Podświetlanie składni i wskazówki dotyczące kursora dla `docker-compose.yml` i `Dockerfile` plików</span><span class="sxs-lookup"><span data-stu-id="369eb-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="369eb-141">Technologia IntelliSense (uzupełnianie) `Dockerfile` dla `docker-compose.yml` plików i</span><span class="sxs-lookup"><span data-stu-id="369eb-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="369eb-142">Zaznaczanie błędów (błędy i ostrzeżenia) dla `Dockerfile` plików</span><span class="sxs-lookup"><span data-stu-id="369eb-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="369eb-143">Paleta poleceń (F1) dla najpopularniejszych poleceń platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="369eb-144">Integracja Eksploratora do zarządzania obrazami i kontenerami</span><span class="sxs-lookup"><span data-stu-id="369eb-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="369eb-145">Wdróż obrazy z DockerHub i rejestrów kontenerów platformy Azure, aby Azure App Service</span><span class="sxs-lookup"><span data-stu-id="369eb-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="369eb-146">Aby zainstalować rozszerzenie platformy Docker, naciśnij kombinację klawiszy Ctrl + Shift + P, wpisz `ext install` polecenie, a następnie uruchom rozszerzenie install, aby wyświetlić listę rozszerzeń portalu Marketplace.</span><span class="sxs-lookup"><span data-stu-id="369eb-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="369eb-147">Następnie wpisz **Docker** , aby przefiltrować wyniki, a następnie wybierz rozszerzenie obsługa platformy Docker, jak przedstawiono na rysunku 4-23.</span><span class="sxs-lookup"><span data-stu-id="369eb-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Widok rozszerzenia Docker dla VS Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="369eb-149">**Rysunek 4-23**.</span><span class="sxs-lookup"><span data-stu-id="369eb-149">**Figure 4-23**.</span></span> <span data-ttu-id="369eb-150">Instalowanie rozszerzenia platformy Docker w Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="369eb-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="369eb-151">Krok 2. Tworzenie pliku dockerfile związanych z istniejącym obrazem (zwykłego systemu operacyjnego lub środowisk deweloperskich, takich jak .NET Core, Node.js i Ruby)</span><span class="sxs-lookup"><span data-stu-id="369eb-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="369eb-152">Musisz utworzyć `DockerFile` obraz niestandardowy do skompilowania i na kontener, który ma zostać wdrożony.</span><span class="sxs-lookup"><span data-stu-id="369eb-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="369eb-153">Jeśli Twoja aplikacja składa się z pojedynczej usługi niestandardowej, będziesz potrzebować jednego z nich `DockerFile` .</span><span class="sxs-lookup"><span data-stu-id="369eb-153">If your app is made up of single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="369eb-154">Jeśli jednak aplikacja składa się z wielu usług (podobnie jak w przypadku architektury mikrousług), będzie potrzebna jedna `Dockerfile` na usługę.</span><span class="sxs-lookup"><span data-stu-id="369eb-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="369eb-155">`DockerFile`Jest to zwykle umieszczane w folderze głównym aplikacji lub usługi i zawiera wymagane polecenia, dzięki czemu platforma Docker wie, jak skonfigurować i uruchomić tę aplikację lub usługę.</span><span class="sxs-lookup"><span data-stu-id="369eb-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="369eb-156">Możesz utworzyć `DockerFile` i dodać go do projektu wraz z kodem (node.js, .NET Core itp.) lub, jeśli jesteś nowym środowiskiem, zapoznaj się z poniższą wskazówką.</span><span class="sxs-lookup"><span data-stu-id="369eb-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="369eb-157">Możesz użyć rozszerzenia Docker, aby poprowadzić Cię podczas korzystania `Dockerfile` z `docker-compose.yml` plików i związanych z kontenerami platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="369eb-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="369eb-158">Na koniec prawdopodobnie napiszesz te rodzaje plików bez tego narzędzia, ale przy użyciu rozszerzenia Docker jest dobrym punktem wyjścia, który przyspiesza uczenie się.</span><span class="sxs-lookup"><span data-stu-id="369eb-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="369eb-159">Na rysunku 4-24 można wyświetlić kroki umożliwiające dodanie plików platformy Docker do projektu przy użyciu rozszerzenia Docker dla VS Code:</span><span class="sxs-lookup"><span data-stu-id="369eb-159">In Figure 4-24, you can see the steps to add the docker files to a project by using the Docker Extension for VS Code:</span></span>

1. <span data-ttu-id="369eb-160">Otwórz paletę poleceń, wpisz "**Docker**" i wybierz pozycję "**Dodaj pliki Docker do obszaru roboczego**".</span><span class="sxs-lookup"><span data-stu-id="369eb-160">Open the command palette, type "**docker**" and select "**Add Docker Files to Workspace**".</span></span>
2. <span data-ttu-id="369eb-161">Wybierz platformę aplikacji (ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="369eb-161">Select Application Platform (ASP.NET Core)</span></span>
3. <span data-ttu-id="369eb-162">Wybierz system operacyjny (Linux)</span><span class="sxs-lookup"><span data-stu-id="369eb-162">Select Operating System (Linux)</span></span>
4. <span data-ttu-id="369eb-163">Uwzględnij opcjonalne pliki Docker Compose</span><span class="sxs-lookup"><span data-stu-id="369eb-163">Include optional Docker Compose files</span></span>
5. <span data-ttu-id="369eb-164">Wprowadź porty do opublikowania (80, 443)</span><span class="sxs-lookup"><span data-stu-id="369eb-164">Enter ports to publish (80, 443)</span></span>
6. <span data-ttu-id="369eb-165">Wybieranie projektu</span><span class="sxs-lookup"><span data-stu-id="369eb-165">Select the project</span></span>

![Kroki dodawania plików platformy Docker z rozszerzeniem platformy Docker](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="369eb-167">**Rysunek 4-24**.</span><span class="sxs-lookup"><span data-stu-id="369eb-167">**Figure 4-24**.</span></span> <span data-ttu-id="369eb-168">Pliki platformy Docker dodane za pomocą polecenia **Dodaj pliki platformy Docker do obszaru roboczego**</span><span class="sxs-lookup"><span data-stu-id="369eb-168">Docker files added using the **Add Docker files to Workspace** command</span></span>

<span data-ttu-id="369eb-169">Po dodaniu pliku dockerfile należy określić, który podstawowy obraz platformy Docker będzie używany (na przykład za pomocą programu `FROM mcr.microsoft.com/dotnet/core/aspnet` ).</span><span class="sxs-lookup"><span data-stu-id="369eb-169">When you add a DockerFile, you specify what base Docker image you'll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="369eb-170">Zwykle utworzysz niestandardowy obraz na podstawie obrazu podstawowego, który można uzyskać z dowolnego oficjalnego repozytorium w [rejestrze usługi Docker Hub](https://hub.docker.com/) (na przykład [obrazu dla platformy .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) lub [dla Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="369eb-170">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

> [!TIP]
> <span data-ttu-id="369eb-171">Należy powtórzyć tę procedurę dla każdego projektu w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="369eb-171">You'll have to repeat this procedure for every project in your application.</span></span> <span data-ttu-id="369eb-172">Jednak rozszerzenie będzie zażądać zastąpienia wygenerowanego pliku z systemem Docker po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="369eb-172">However, the extension will ask to overwrite the generated docker-compose file after the first time.</span></span> <span data-ttu-id="369eb-173">Należy odpowiedzieć, aby nie nadpisać, dlatego rozszerzenie tworzy osobne pliki do redagowania platformy Docker, które można następnie scalić przed uruchomieniem systemu Docker — tworzenie.</span><span class="sxs-lookup"><span data-stu-id="369eb-173">You should reply to not overwrite it, so the extension creates separate docker-compose files, that you can then merge by hand, prior to running docker-compose.</span></span>

<span data-ttu-id="369eb-174">**_Użyj istniejącego oficjalnego obrazu platformy Docker_**</span><span class="sxs-lookup"><span data-stu-id="369eb-174">**_Use an existing official Docker image_**</span></span>

<span data-ttu-id="369eb-175">Korzystanie z oficjalnego repozytorium stosu języka z numerem wersji zapewnia, że te same funkcje językowe są dostępne na wszystkich komputerach (w tym na etapie projektowania, testowania i produkcji).</span><span class="sxs-lookup"><span data-stu-id="369eb-175">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="369eb-176">Poniżej znajduje się przykład pliku dockerfile dla kontenera .NET Core:</span><span class="sxs-lookup"><span data-stu-id="369eb-176">The following is a sample DockerFile for a .NET Core container:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
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

<span data-ttu-id="369eb-177">W tym przypadku obraz jest oparty na wersji 3,1 ASP.NET Core oficjalnego obrazu platformy Docker (wiele rozwiązań dla systemów Linux i Windows), zgodnie z wierszem `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` .</span><span class="sxs-lookup"><span data-stu-id="369eb-177">In this case, the image is based on version 3.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="369eb-178">(Aby uzyskać więcej informacji na temat tego tematu, zobacz stronę [ASP.NET Core Docker](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) i stronę [obrazu platformy Docker programu .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) ).</span><span class="sxs-lookup"><span data-stu-id="369eb-178">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="369eb-179">W pliku dockerfile można także nakazać platformie Docker nasłuchiwanie portu TCP, który będzie używany w czasie wykonywania (na przykład port 80 lub 443).</span><span class="sxs-lookup"><span data-stu-id="369eb-179">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80 or 443).</span></span>

<span data-ttu-id="369eb-180">Możesz określić dodatkowe ustawienia konfiguracji w pliku dockerfile, w zależności od używanego języka i platformy.</span><span class="sxs-lookup"><span data-stu-id="369eb-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="369eb-181">Na przykład `ENTRYPOINT` wiersz z poleceniem `["dotnet", "WebMvcApplication.dll"]` instruuje platformę Docker, aby uruchomić aplikację .NET Core.</span><span class="sxs-lookup"><span data-stu-id="369eb-181">For instance, the `ENTRYPOINT` line with `["dotnet", "WebMvcApplication.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="369eb-182">Jeśli używasz zestawu SDK i interfejs wiersza polecenia platformy .NET Core ( `dotnet CLI` ) do kompilowania i uruchamiania aplikacji .NET, to ustawienie będzie inne.</span><span class="sxs-lookup"><span data-stu-id="369eb-182">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="369eb-183">Kluczowym punktem jest to, że wiersz punktu wejścia i inne ustawienia zależą od języka i platformy wybranej dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="369eb-183">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="369eb-184">Aby uzyskać więcej informacji na temat tworzenia obrazów platformy Docker dla aplikacji platformy .NET Core, przejdź do <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images> .</span><span class="sxs-lookup"><span data-stu-id="369eb-184">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="369eb-185">Aby dowiedzieć się więcej na temat tworzenia własnych obrazów, przejdź do <https://docs.docker.com/engine/tutorials/dockerimages/> .</span><span class="sxs-lookup"><span data-stu-id="369eb-185">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="369eb-186">**Używanie repozytoriów obrazów wieloskładnikowych**</span><span class="sxs-lookup"><span data-stu-id="369eb-186">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="369eb-187">Nazwa pojedynczego obrazu w repozytorium może zawierać warianty platformy, takie jak obraz systemu Linux i obraz Windows.</span><span class="sxs-lookup"><span data-stu-id="369eb-187">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="369eb-188">Ta funkcja umożliwia dostawcom, takim jak firma Microsoft (twórcy obrazów podstawowych), tworzenie jednego repozytorium w celu pokrycia wielu platform (to jest Linux i Windows).</span><span class="sxs-lookup"><span data-stu-id="369eb-188">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="369eb-189">Na przykład repozytorium [dotnet/rdzeń/ASPNET](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) dostępne w rejestrze usługi Docker Hub zapewnia obsługę systemu Linux i Windows nano Server przy użyciu tej samej nazwy obrazu.</span><span class="sxs-lookup"><span data-stu-id="369eb-189">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="369eb-190">Ściąganie obrazu [dotnet/Core/ASPNET](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) z hosta z systemem Windows powoduje pobranie wariantu systemu Windows, podczas gdy ściąganie tej samej nazwy obrazu z hosta z systemem Linux jest ściągane.</span><span class="sxs-lookup"><span data-stu-id="369eb-190">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="369eb-191">**_Tworzenie obrazu podstawowego od podstaw_**</span><span class="sxs-lookup"><span data-stu-id="369eb-191">**_Create your base image from scratch_**</span></span>

<span data-ttu-id="369eb-192">Możesz utworzyć własny obraz podstawowy platformy Docker od podstaw, jak wyjaśniono w tym [artykule](https://docs.docker.com/engine/userguide/eng-image/baseimages/) z platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="369eb-192">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="369eb-193">Ten scenariusz prawdopodobnie nie jest najlepszym rozwiązaniem, jeśli właśnie zaczynasz pracę z platformą Docker, ale jeśli chcesz ustawić określone bity obrazu podstawowego, możesz to zrobić.</span><span class="sxs-lookup"><span data-stu-id="369eb-193">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="369eb-194">Krok 3. Tworzenie niestandardowych obrazów platformy Docker osadzania w niej usługi</span><span class="sxs-lookup"><span data-stu-id="369eb-194">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="369eb-195">Dla każdej usługi niestandardowej, która składa się z aplikacji, konieczne będzie utworzenie powiązanego obrazu.</span><span class="sxs-lookup"><span data-stu-id="369eb-195">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="369eb-196">Jeśli aplikacja składa się z pojedynczej usługi lub aplikacji sieci Web, będzie potrzebny tylko jeden obraz.</span><span class="sxs-lookup"><span data-stu-id="369eb-196">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="369eb-197">Podczas wzięcia pod uwagę "przepływu pracy DevOps pętla zewnętrzna" obrazy zostaną utworzone przez zautomatyzowany proces kompilacji po każdym wypchnięciu kodu źródłowego do repozytorium git (ciągłej integracji), dzięki czemu obrazy zostaną utworzone w tym środowisku globalnym z kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="369eb-197">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="369eb-198">Jednak przed rozważeniem przechodzenia do tej trasy z pętlą zewnętrzną należy upewnić się, że aplikacja platformy Docker rzeczywiście działa prawidłowo, aby nie wypchnięcia kodu, który może nie działać prawidłowo w systemie kontroli źródła (git itp.).</span><span class="sxs-lookup"><span data-stu-id="369eb-198">But before you consider going to that outer-loop route, you need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="369eb-199">W związku z tym każdy Deweloper musi najpierw wykonać cały proces pętli wewnętrznej, aby przetestować lokalnie i kontynuować programowanie do momentu, gdy chcą wypchnąć kompletną funkcję lub zmienić system kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="369eb-199">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="369eb-200">Aby utworzyć obraz w środowisku lokalnym i przy użyciu pliku dockerfile, można użyć polecenia Docker Build, jak pokazano na rysunku 4-25, ponieważ jest już Tagi obrazu dla Ciebie i tworzy obrazy dla wszystkich usług w aplikacji za pomocą prostego polecenia.</span><span class="sxs-lookup"><span data-stu-id="369eb-200">To create an image in your local environment and using the DockerFile, you can use the docker build command, as shown in Figure 4-25, because it already tags the image for you and builds the images for all services in the application with a simple command.</span></span>

![Zrzut ekranu przedstawiający dane wyjściowe konsoli polecenia Docker-Zredaguj Build.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="369eb-202">**Rysunek 4-25**.</span><span class="sxs-lookup"><span data-stu-id="369eb-202">**Figure 4-25**.</span></span> <span data-ttu-id="369eb-203">Uruchamianie kompilacji platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-203">Running docker build</span></span>

<span data-ttu-id="369eb-204">Opcjonalnie, zamiast bezpośrednio z `docker build` poziomu folderu projektu, można najpierw wygenerować folder do wdrożenia z bibliotekami platformy .NET wymaganymi przy użyciu `dotnet publish` polecenia Uruchom, a następnie uruchomić polecenie `docker build` .</span><span class="sxs-lookup"><span data-stu-id="369eb-204">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="369eb-205">W tym przykładzie tworzony jest obraz platformy Docker o nazwie `explore-docker-vscode/webapi:latest` ( `:latest` jest to tag, taki jak określona wersja).</span><span class="sxs-lookup"><span data-stu-id="369eb-205">This example creates a Docker image with the name `explore-docker-vscode/webapi:latest` (`:latest` is a tag, like a specific version).</span></span> <span data-ttu-id="369eb-206">Ten krok można wykonać dla każdego niestandardowego obrazu, który trzeba utworzyć dla złożonej aplikacji platformy Docker z kilkoma kontenerami.</span><span class="sxs-lookup"><span data-stu-id="369eb-206">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span> <span data-ttu-id="369eb-207">Jednak w następnej sekcji zobaczymy, że jest to łatwiejsze w użyciu `docker-compose` .</span><span class="sxs-lookup"><span data-stu-id="369eb-207">However, we'll see in the next section that it's easier to do this using `docker-compose`.</span></span>

<span data-ttu-id="369eb-208">Istniejące obrazy można znaleźć w lokalnym repozytorium (na komputerze deweloperskim) przy użyciu `docker images` polecenia, jak pokazano na rysunku 4-26.</span><span class="sxs-lookup"><span data-stu-id="369eb-208">You can find the existing images in your local repository (your development machine) by using the `docker images` command, as illustrated in Figure 4-26.</span></span>

![Dane wyjściowe konsoli z obrazów platformy Docker, pokazujące istniejące obrazy.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="369eb-210">**Rysunek 4-26**.</span><span class="sxs-lookup"><span data-stu-id="369eb-210">**Figure 4-26**.</span></span> <span data-ttu-id="369eb-211">Wyświetlanie istniejących obrazów przy użyciu obrazów platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-211">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="369eb-212">Krok 4. Definiowanie usług w Docker-Compose. yml podczas tworzenia złożonej aplikacji platformy Docker z wieloma usługami</span><span class="sxs-lookup"><span data-stu-id="369eb-212">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="369eb-213">Przy użyciu `docker-compose.yml` pliku można zdefiniować zestaw powiązanych usług, które mają zostać wdrożone jako aplikacja składająca się z poleceniami wdrażania wyjaśnionymi w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="369eb-213">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="369eb-214">Utwórz ten plik w folderze głównym lub głównym rozwiązania. powinna zawierać zawartość podobną do pokazanej w tym `docker-compose.yml` pliku:</span><span class="sxs-lookup"><span data-stu-id="369eb-214">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="369eb-215">W tym konkretnym przypadku ten plik definiuje trzy usługi: usługę internetowego interfejsu API (usługę niestandardową), aplikację sieci Web i usługę Redis (popularne usługi pamięci podręcznej).</span><span class="sxs-lookup"><span data-stu-id="369eb-215">In this particular case, this file defines three services: the web API service (your custom service), a web application, and the Redis service (a popular cache service).</span></span> <span data-ttu-id="369eb-216">Każda usługa zostanie wdrożona jako kontener, dlatego należy użyć konkretnego obrazu platformy Docker dla każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="369eb-216">Each service will be deployed as a container, so you need to use a concrete Docker image for each.</span></span> <span data-ttu-id="369eb-217">Dla tej konkretnej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="369eb-217">For this particular application:</span></span>

- <span data-ttu-id="369eb-218">Usługa internetowego interfejsu API została skompilowana z pliku dockerfile w `src/WebApi/Dockerfile` katalogu.</span><span class="sxs-lookup"><span data-stu-id="369eb-218">The web API service is built from the DockerFile in the `src/WebApi/Dockerfile` directory.</span></span>

- <span data-ttu-id="369eb-219">Port 51080 hosta jest przekazywany do uwidocznionego portu 80 w `webapi` kontenerze.</span><span class="sxs-lookup"><span data-stu-id="369eb-219">The host port 51080 is forwarded to the exposed port 80 on the `webapi` container.</span></span>

- <span data-ttu-id="369eb-220">Usługa internetowego interfejsu API zależy od usługi Redis</span><span class="sxs-lookup"><span data-stu-id="369eb-220">The web API service depends on the Redis service</span></span>

- <span data-ttu-id="369eb-221">Aplikacja sieci Web uzyskuje dostęp do usługi internetowego interfejsu API przy użyciu adresu wewnętrznego: `http://webapi` .</span><span class="sxs-lookup"><span data-stu-id="369eb-221">The web application accesses the web API service using the internal address: `http://webapi`.</span></span>

- <span data-ttu-id="369eb-222">Usługa Redis używa [najnowszego publicznego obrazu Redis](https://hub.docker.com/_/redis/) pobranego z rejestru usługi Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="369eb-222">The Redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="369eb-223">[Redis](https://redis.io/) to popularny system pamięci podręcznej dla aplikacji po stronie serwera.</span><span class="sxs-lookup"><span data-stu-id="369eb-223">[Redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="369eb-224">Krok 5. Kompilowanie i uruchamianie aplikacji platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-224">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="369eb-225">Jeśli aplikacja ma tylko jeden kontener, wystarczy ją uruchomić, wdrażając ją na hoście platformy Docker (maszynie wirtualnej lub serwerze fizycznym).</span><span class="sxs-lookup"><span data-stu-id="369eb-225">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="369eb-226">Jeśli jednak aplikacja składa się z wielu usług, musisz _ją utworzyć_.</span><span class="sxs-lookup"><span data-stu-id="369eb-226">However, if your app is made up of multiple services, you need to _compose it_, too.</span></span> <span data-ttu-id="369eb-227">Zobaczmy różne opcje.</span><span class="sxs-lookup"><span data-stu-id="369eb-227">Let's see the different options.</span></span>

<span data-ttu-id="369eb-228">**_Opcja A: uruchamianie jednego kontenera lub usługi_**</span><span class="sxs-lookup"><span data-stu-id="369eb-228">**_Option A: Run a single container or service_**</span></span>

<span data-ttu-id="369eb-229">Obraz platformy Docker można uruchomić przy użyciu polecenia Docker Run, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="369eb-229">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 50080:80 explore-docker-vscode/webapp:latest
```

<span data-ttu-id="369eb-230">W przypadku tego konkretnego wdrożenia będziemy przekierowywać żądania wysyłane do portu 50080 na hoście do wewnętrznego portu 80.</span><span class="sxs-lookup"><span data-stu-id="369eb-230">For this particular deployment, we'll be redirecting requests sent to port 50080 on the host to the internal port 80.</span></span>

<span data-ttu-id="369eb-231">**_Opcja B: redagowanie i uruchamianie aplikacji z wieloma kontenerami_**</span><span class="sxs-lookup"><span data-stu-id="369eb-231">**_Option B: Compose and run a multiple-container application_**</span></span>

<span data-ttu-id="369eb-232">W większości scenariuszy przedsiębiorstwa aplikacja platformy Docker będzie składać się z wielu usług.</span><span class="sxs-lookup"><span data-stu-id="369eb-232">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="369eb-233">W takich przypadkach można uruchomić `docker-compose up` polecenie (rysunek 4-27), które będzie używać wcześniej utworzonego pliku Docker-Compose. yml.</span><span class="sxs-lookup"><span data-stu-id="369eb-233">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you created previously.</span></span> <span data-ttu-id="369eb-234">Uruchomienie tego polecenia kompiluje wszystkie obrazy niestandardowe i wdraża aplikację złożoną ze wszystkimi powiązanymi kontenerami.</span><span class="sxs-lookup"><span data-stu-id="369eb-234">Running this command builds all custom images and deploys the composed application with all of its related containers.</span></span>

![Dane wyjściowe konsoli z platformy Docker — tworzenie.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="369eb-236">**Rysunek 4-27**.</span><span class="sxs-lookup"><span data-stu-id="369eb-236">**Figure 4-27**.</span></span> <span data-ttu-id="369eb-237">Wyniki uruchamiania polecenia "Docker-Zredaguj do"</span><span class="sxs-lookup"><span data-stu-id="369eb-237">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="369eb-238">Po uruchomieniu `docker-compose up` programu aplikacja i powiązane z nim kontenery są wdrażane na hoście platformy Docker, jak pokazano na rysunku 4-28 w reprezentacji maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="369eb-238">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Maszyna wirtualna z uruchomioną funkcją wielokontenera aplikacji.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="369eb-240">**Rysunek 4-28**.</span><span class="sxs-lookup"><span data-stu-id="369eb-240">**Figure 4-28**.</span></span> <span data-ttu-id="369eb-241">Maszyna wirtualna z wdrożonymi kontenerami platformy Docker</span><span class="sxs-lookup"><span data-stu-id="369eb-241">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="369eb-242">Krok 6. Testowanie aplikacji platformy Docker (lokalnie, na lokalnej maszynie wirtualnej z płytą CD)</span><span class="sxs-lookup"><span data-stu-id="369eb-242">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="369eb-243">Ten krok będzie się różnić w zależności od tego, co aplikacja działa.</span><span class="sxs-lookup"><span data-stu-id="369eb-243">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="369eb-244">W prostym interfejsie API sieci Web platformy .NET Core "Hello world" wdrożonym jako pojedynczy kontener lub usługa, wystarczy uzyskać dostęp do usługi, podając port TCP określony w pliku dockerfile.</span><span class="sxs-lookup"><span data-stu-id="369eb-244">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="369eb-245">Na hoście platformy Docker Otwórz przeglądarkę i przejdź do tej witryny. powinna zostać wyświetlona aplikacja/usługa, jak pokazano na rysunku 4-29.</span><span class="sxs-lookup"><span data-stu-id="369eb-245">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Widok przeglądarki odpowiedzi z localhost/API/Values.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="369eb-247">**Rysunek 4-29**.</span><span class="sxs-lookup"><span data-stu-id="369eb-247">**Figure 4-29**.</span></span> <span data-ttu-id="369eb-248">Lokalne testowanie aplikacji platformy Docker przy użyciu przeglądarki</span><span class="sxs-lookup"><span data-stu-id="369eb-248">Testing your Docker application locally by using the browser</span></span>

<span data-ttu-id="369eb-249">Należy zauważyć, że korzysta on z portu 50080, ale wewnętrznie jest przekierowywany do portu 80, ponieważ został on wdrożony w programie `docker compose` , jak wyjaśniono wcześniej.</span><span class="sxs-lookup"><span data-stu-id="369eb-249">Note that it's using port 50080, but internally it's being redirected to port 80, because that's how it was deployed with `docker compose`, as explained earlier.</span></span>

<span data-ttu-id="369eb-250">Można to przetestować przy użyciu przeglądarki korzystającej z wypełniania z terminalu, jak przedstawiono na rysunku 4-30.</span><span class="sxs-lookup"><span data-stu-id="369eb-250">You can test this by using the browser using CURL from the terminal, as depicted in Figure 4-30.</span></span>

![Uzyskano wynik zwinięcie z http://localhost:51080/WeatherForecast](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="369eb-252">**Rysunek 4-30**.</span><span class="sxs-lookup"><span data-stu-id="369eb-252">**Figure 4-30**.</span></span> <span data-ttu-id="369eb-253">Lokalne testowanie aplikacji platformy Docker przy użyciu programu ZWINIĘCIE</span><span class="sxs-lookup"><span data-stu-id="369eb-253">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="369eb-254">**Debugowanie kontenera działającego na platformie Docker**</span><span class="sxs-lookup"><span data-stu-id="369eb-254">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="369eb-255">Visual Studio Code obsługuje debugowanie platformy Docker, jeśli używasz Node.js i innych platform, takich jak kontenery .NET Core.</span><span class="sxs-lookup"><span data-stu-id="369eb-255">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="369eb-256">Można również debugować kontenery .NET Core lub .NET Framework w programie Docker podczas korzystania z programu Visual Studio dla systemu Windows lub Mac, zgodnie z opisem w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="369eb-256">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="369eb-257">Aby dowiedzieć się więcej na temat debugowania Node.js kontenerów platformy Docker, zobacz <https://blog.docker.com/2016/07/live-debugging-docker/> i <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more> .</span><span class="sxs-lookup"><span data-stu-id="369eb-257">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="369eb-258">[Poprzedni](docker-apps-development-environment.md) 
>  [Dalej](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="369eb-258">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
