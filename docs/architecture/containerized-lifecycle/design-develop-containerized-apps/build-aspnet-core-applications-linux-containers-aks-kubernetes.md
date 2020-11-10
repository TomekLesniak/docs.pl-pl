---
title: Kompiluj ASP.NET Core aplikacje wdrożone jako kontenery systemu Linux w klastrach AKS/Kubernetes
description: Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 831d2372131e20788d0f48190eb8c600aa02485c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440832"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="93ece-103">Kompiluj ASP.NET Core aplikacje wdrożone jako kontenery systemu Linux w programie Orchestrator AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="93ece-103">Build ASP.NET Core applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="93ece-104">Usługa Azure Kubernetes Services (AKS) to zarządzane przez platformę Azure usługi, które upraszczają wdrażanie kontenerów i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="93ece-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="93ece-105">Główne funkcje AKS są następujące:</span><span class="sxs-lookup"><span data-stu-id="93ece-105">AKS main features are:</span></span>

- <span data-ttu-id="93ece-106">Oparta na platformie Azure płaszczyzna kontroli</span><span class="sxs-lookup"><span data-stu-id="93ece-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="93ece-107">Automatyczne uaktualnienia</span><span class="sxs-lookup"><span data-stu-id="93ece-107">Automated upgrades</span></span>
- <span data-ttu-id="93ece-108">Samonaprawianie</span><span class="sxs-lookup"><span data-stu-id="93ece-108">Self-healing</span></span>
- <span data-ttu-id="93ece-109">Skalowanie konfigurowalne przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="93ece-109">User-configurable scaling</span></span>
- <span data-ttu-id="93ece-110">Prostsze środowisko użytkownika dla deweloperów i operatorów klastrów.</span><span class="sxs-lookup"><span data-stu-id="93ece-110">Simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="93ece-111">W poniższych przykładach pokazano, jak utworzyć aplikację ASP.NET Core 3,1 działającą w systemie Linux i wdrożyć ją w klastrze AKS na platformie Azure, podczas gdy programowanie odbywa się przy użyciu programu Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="93ece-111">The following examples explore the creation of an ASP.NET Core 3.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2019.</span></span>

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a><span data-ttu-id="93ece-112">Tworzenie projektu ASP.NET Core przy użyciu programu Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="93ece-112">Creating the ASP.NET Core Project using Visual Studio 2019</span></span>

<span data-ttu-id="93ece-113">ASP.NET Core jest platformą programistyczną ogólnego przeznaczenia obsługiwaną przez firmę Microsoft i społeczność programu .NET w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="93ece-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="93ece-114">Jest to międzyplatformowe, pomocnicze systemy Windows, macOS i Linux oraz mogą być używane w scenariuszach urządzeń, chmur i osadzonych/IoT.</span><span class="sxs-lookup"><span data-stu-id="93ece-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="93ece-115">Ten przykład korzysta z kilku prostych projektów opartych na szablonach programu Visual Studio, więc nie potrzebujesz więcej informacji na temat tworzenia przykładu.</span><span class="sxs-lookup"><span data-stu-id="93ece-115">This example uses a couple of simple projects based on Visual Studio templates, so you don't need much additional knowledge to create the sample.</span></span> <span data-ttu-id="93ece-116">Wystarczy utworzyć projekt przy użyciu standardowego szablonu, który zawiera wszystkie elementy, aby uruchomić niewielki projekt z interfejsem API REST i aplikacją internetową ze stronami Razor przy użyciu technologii ASP.NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="93ece-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API and a Web App with Razor pages, using ASP.NET Core 3.1 technology.</span></span>

![Dodaj nowe okno projektu w programie Visual Studio, wybierając ASP.NET Core aplikacji sieci Web.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

<span data-ttu-id="93ece-118">**Rysunek 4-35**.</span><span class="sxs-lookup"><span data-stu-id="93ece-118">**Figure 4-35**.</span></span> <span data-ttu-id="93ece-119">Tworzenie aplikacji sieci Web ASP.NET Core w programie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="93ece-119">Creating an ASP.NET Core Web Application in Visual Studio 2019.</span></span>

<span data-ttu-id="93ece-120">Aby utworzyć przykładowy projekt w programie Visual Studio, wybierz pozycję **plik**  >  **Nowy**  >  **projekt** , wybierz typ projektu **sieci Web** , a następnie szablon **aplikacji sieci Web ASP.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="93ece-120">To create the sample project in Visual Studio, select **File** > **New** > **Project** , select the **Web** project type and then the **ASP.NET Core Web Application** template.</span></span> <span data-ttu-id="93ece-121">Możesz również wyszukać szablon, jeśli będzie potrzebny.</span><span class="sxs-lookup"><span data-stu-id="93ece-121">You can also search for the template if you need it.</span></span>

<span data-ttu-id="93ece-122">Następnie wprowadź nazwę i lokalizację aplikacji, jak pokazano na następnym obrazie.</span><span class="sxs-lookup"><span data-stu-id="93ece-122">Then enter the application name and location as shown in the next image.</span></span>

![Wprowadź nazwę projektu i lokalizację.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

<span data-ttu-id="93ece-124">**Rysunek 4-36**.</span><span class="sxs-lookup"><span data-stu-id="93ece-124">**Figure 4-36**.</span></span> <span data-ttu-id="93ece-125">Wprowadź nazwę i lokalizację projektu w programie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="93ece-125">Enter the project name and location in Visual Studio 2019.</span></span>

<span data-ttu-id="93ece-126">Upewnij się, że wybrano ASP.NET Core 3,1 jako strukturę.</span><span class="sxs-lookup"><span data-stu-id="93ece-126">Verify that you've selected ASP.NET Core 3.1 as the framework.</span></span> <span data-ttu-id="93ece-127">Program .NET Core 3,1 jest dołączony do najnowszej wersji programu Visual Studio 2019 i jest automatycznie instalowany i konfigurowany podczas instalowania programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93ece-127">.NET Core 3.1 is included in the latest release of Visual Studio 2019 and is automatically installed and configured for you when you install Visual Studio.</span></span>

![Okno dialogowe programu Visual Studio, w którym można wybrać typ aplikacji sieci Web ASP.NET Core przy użyciu opcji API.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

<span data-ttu-id="93ece-129">**Rysunek 4-37**.</span><span class="sxs-lookup"><span data-stu-id="93ece-129">**Figure 4-37**.</span></span> <span data-ttu-id="93ece-130">Wybieranie ASP.NET CORE 3,1 i typ projektu interfejsu API sieci Web</span><span class="sxs-lookup"><span data-stu-id="93ece-130">Selecting ASP.NET CORE 3.1 and Web API project type</span></span>

<span data-ttu-id="93ece-131">Obsługa platformy Docker nie jest teraz włączona, wystarczy ją wyświetlić po utworzeniu projektu.</span><span class="sxs-lookup"><span data-stu-id="93ece-131">Notice Docker support is not enabled now, just to show it can be done after project creation.</span></span>

<span data-ttu-id="93ece-132">Jeśli masz poprzednią wersję programu .NET Core, możesz pobrać i zainstalować wersję 3,1 z programu <https://dotnet.microsoft.com/download> .</span><span class="sxs-lookup"><span data-stu-id="93ece-132">If you have any previous version of .NET Core, you can download and install the 3.1 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="93ece-133">Aby w dowolnym momencie można było wyświetlić projekt "przekształcać", możesz dodać obsługę platformy Docker teraz.</span><span class="sxs-lookup"><span data-stu-id="93ece-133">To show you can "Dockerize" your project at any time, you'll add Docker support now.</span></span> <span data-ttu-id="93ece-134">Kliknij prawym przyciskiem myszy węzeł projektu w Eksplorator rozwiązań a następnie wybierz polecenie **Dodaj**  >  **obsługę platformy Docker** w menu kontekstowym.</span><span class="sxs-lookup"><span data-stu-id="93ece-134">So right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Opcja menu kontekstowego umożliwiająca dodanie obsługi platformy Docker do istniejącego projektu: kliknij prawym przyciskiem myszy (na projekcie) > Dodaj > obsługa platformy Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

<span data-ttu-id="93ece-136">**Rysunek 4-38**.</span><span class="sxs-lookup"><span data-stu-id="93ece-136">**Figure 4-38**.</span></span> <span data-ttu-id="93ece-137">Dodawanie obsługi platformy Docker do istniejącego projektu</span><span class="sxs-lookup"><span data-stu-id="93ece-137">Adding Docker support to an existing project</span></span>

<span data-ttu-id="93ece-138">Aby ukończyć Dodawanie obsługi platformy Docker, możesz wybrać system Windows lub Linux.</span><span class="sxs-lookup"><span data-stu-id="93ece-138">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="93ece-139">W takim przypadku wybierz pozycję **Linux**.</span><span class="sxs-lookup"><span data-stu-id="93ece-139">In this case, select **Linux**.</span></span>

![Opcja okna dialogowego umożliwiającego wybranie docelowego systemu operacyjnego dla pliku dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

<span data-ttu-id="93ece-141">**Rysunek 4-39**.</span><span class="sxs-lookup"><span data-stu-id="93ece-141">**Figure 4-39**.</span></span> <span data-ttu-id="93ece-142">Wybieranie kontenerów systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="93ece-142">Selecting Linux containers.</span></span>

<span data-ttu-id="93ece-143">Dzięki tym prostym krokom aplikacja ASP.NET Core 3,1 działa w kontenerze systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="93ece-143">With these simple steps, you have your ASP.NET Core 3.1 application running on a Linux container.</span></span>

<span data-ttu-id="93ece-144">W podobny sposób można również dodać bardzo prosty projekt **webapp** (rysunek 4-40) do korzystania z punktu końcowego internetowego interfejsu API, chociaż szczegółowe informacje nie zostały omówione w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="93ece-144">In a similar way, you can also add a very simple **WebApp** project (Figure 4-40) to consume the web API endpoint, although the details are not discussed here.</span></span>

<span data-ttu-id="93ece-145">Następnie można dodać obsługę programu Orchestrator dla projektu **WebAPI** , jak pokazano poniżej, w obrazie 4-40.</span><span class="sxs-lookup"><span data-stu-id="93ece-145">After that, you add orchestrator support for your **WebApi** project as shown next, in image 4-40.</span></span>

![Dodawanie obsługi programu Orchestrator do projektu WebApi](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

<span data-ttu-id="93ece-147">**Rysunek 4-40**.</span><span class="sxs-lookup"><span data-stu-id="93ece-147">**Figure 4-40**.</span></span> <span data-ttu-id="93ece-148">Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .</span><span class="sxs-lookup"><span data-stu-id="93ece-148">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="93ece-149">Po wybraniu `Docker Compose` opcji, która jest precyzyjna dla rozwoju lokalnego, program Visual Studio dodaje projekt Docker-Zredaguj z plikami z systemem Docker, jak pokazano w obrazie 4-41.</span><span class="sxs-lookup"><span data-stu-id="93ece-149">When you choose the `Docker Compose` option, which is fine for local development, Visual Studio adds the docker-compose project, with the docker-compose files as shown in image 4-41.</span></span>

![Docker — tworzenie i dodawanie do rozwiązania](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

<span data-ttu-id="93ece-151">**Rysunek 4-41**.</span><span class="sxs-lookup"><span data-stu-id="93ece-151">**Figure 4-41**.</span></span> <span data-ttu-id="93ece-152">Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .</span><span class="sxs-lookup"><span data-stu-id="93ece-152">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="93ece-153">Pliki początkowe dodane są podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="93ece-153">The initial files added are similar to these ones:</span></span>

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

<span data-ttu-id="93ece-154">Aby aplikacja była uruchamiana z Docker Compose wystarczy tylko wprowadzić kilka dostosowań `docker-compose.override.yml`</span><span class="sxs-lookup"><span data-stu-id="93ece-154">To have you app running with Docker Compose you just have to make a few tweaks to `docker-compose.override.yml`</span></span>

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

<span data-ttu-id="93ece-155">Teraz możesz uruchomić aplikację przy użyciu klawisza **F5** lub przy użyciu przycisku **Odtwórz** lub klawisza **Ctrl + F5** , wybierając projekt Docker-zredaguj, jak pokazano na ilustracji 4-42.</span><span class="sxs-lookup"><span data-stu-id="93ece-155">Now you can run your application with the **F5** key, or by using the **Play** button, or the **Ctrl+F5** key, selecting the docker-compose project, as shown in image 4-42.</span></span>

![Uruchamianie platformy Docker — redagowanie projektu w programie Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

<span data-ttu-id="93ece-157">**Rysunek 4-42**.</span><span class="sxs-lookup"><span data-stu-id="93ece-157">**Figure 4-42**.</span></span> <span data-ttu-id="93ece-158">Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .</span><span class="sxs-lookup"><span data-stu-id="93ece-158">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="93ece-159">W przypadku uruchamiania aplikacji platformy Docker, jak wyjaśniono, uzyskasz następujące korzyści:</span><span class="sxs-lookup"><span data-stu-id="93ece-159">When running the docker-compose application as explained, you get:</span></span>

1. <span data-ttu-id="93ece-160">Skompilowane obrazy i kontenery utworzone zgodnie z plikiem dla platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="93ece-160">The images built and containers created as per the docker-compose file.</span></span>
2. <span data-ttu-id="93ece-161">Przeglądarka jest otwarta w adresie skonfigurowanym w oknie dialogowym "właściwości" dla `docker-compose` projektu.</span><span class="sxs-lookup"><span data-stu-id="93ece-161">The browser open in the address configured in the "Properties" dialog for the `docker-compose` project.</span></span>
3. <span data-ttu-id="93ece-162">Otwarte okno **kontenera** (w programie Visual Studio 2019 w wersji 16,4 lub nowszej).</span><span class="sxs-lookup"><span data-stu-id="93ece-162">The **Container** window open (in Visual Studio 2019 version 16.4 and later).</span></span>
4. <span data-ttu-id="93ece-163">Obsługa debugera dla wszystkich projektów w rozwiązaniu, jak pokazano na poniższych ilustracjach.</span><span class="sxs-lookup"><span data-stu-id="93ece-163">Debugger support for all projects in the solution, as shown in the following images.</span></span>

<span data-ttu-id="93ece-164">Otwarto przeglądarkę:</span><span class="sxs-lookup"><span data-stu-id="93ece-164">Browser opened:</span></span>

![Widok przeglądarki z uruchomioną aplikacją sieci Web](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

<span data-ttu-id="93ece-166">**Rysunek 4-43**.</span><span class="sxs-lookup"><span data-stu-id="93ece-166">**Figure 4-43**.</span></span> <span data-ttu-id="93ece-167">Okno przeglądarki z aplikacją uruchomioną w wielu kontenerach.</span><span class="sxs-lookup"><span data-stu-id="93ece-167">Browser window with an application running on multiple containers.</span></span>

<span data-ttu-id="93ece-168">Okno kontenerów:</span><span class="sxs-lookup"><span data-stu-id="93ece-168">Containers window:</span></span>

![Okno "kontenery" programu Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

<span data-ttu-id="93ece-170">**Rysunek 4-44**.</span><span class="sxs-lookup"><span data-stu-id="93ece-170">**Figure 4-44**.</span></span> <span data-ttu-id="93ece-171">Okno "kontenery" programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93ece-171">Visual Studio "Containers" window</span></span>

<span data-ttu-id="93ece-172">Okno **kontenerów** pozwala wyświetlić uruchomione kontenery, przeglądać dostępne obrazy, wyświetlać zmienne środowiskowe, dzienniki i mapowania portów, sprawdzać system plików, dołączać debuger lub otwierać okno terminalu w środowisku kontenera.</span><span class="sxs-lookup"><span data-stu-id="93ece-172">The **Containers** window lets you view running containers, browse available images, view environment variables, logs, and port mappings, inspect the filesystem, attach a debugger, or open a terminal window inside the container environment.</span></span>

<span data-ttu-id="93ece-173">Jak widać, integracja między programem Visual Studio 2019 i platformą Docker jest całkowicie ukierunkowana na produktywność dewelopera.</span><span class="sxs-lookup"><span data-stu-id="93ece-173">As you can see, the integration between Visual Studio 2019 and Docker is completely oriented to the developer's productivity.</span></span>

<span data-ttu-id="93ece-174">Oczywiście można również wyświetlić listę obrazów przy użyciu `docker images` polecenia.</span><span class="sxs-lookup"><span data-stu-id="93ece-174">Of course, you can also list the images using the `docker images` command.</span></span> <span data-ttu-id="93ece-175">Powinny być widoczne `webapi` obrazy i `webapp` z `dev` tagami utworzonymi przez automatyczne wdrażanie naszego projektu przy użyciu programu Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="93ece-175">You should see the `webapi` and `webapp` images with the `dev` tags created by the automatic deployment of our project with Visual Studio 2019.</span></span>

```console
docker images
```

![Dane wyjściowe konsoli z polecenia Docker images, wyświetla listę z: Repository, tag, Image ID, Created (Date) i size.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

<span data-ttu-id="93ece-177">**Rysunek 4-45**.</span><span class="sxs-lookup"><span data-stu-id="93ece-177">**Figure 4-45**.</span></span> <span data-ttu-id="93ece-178">Widok obrazów platformy Docker</span><span class="sxs-lookup"><span data-stu-id="93ece-178">View of Docker images</span></span>

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a><span data-ttu-id="93ece-179">Zarejestruj rozwiązanie w Azure Container Registry (ACR)</span><span class="sxs-lookup"><span data-stu-id="93ece-179">Register the Solution in an Azure Container Registry (ACR)</span></span>

<span data-ttu-id="93ece-180">Można przekazać obrazy do [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), ale można również użyć usługi Docker Hub lub innego rejestru, dzięki czemu obrazy można wdrożyć w klastrze AKS z tego rejestru.</span><span class="sxs-lookup"><span data-stu-id="93ece-180">You can upload the images to the [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), but you could also use Docker Hub or any other registry, so the images can be deployed to the AKS cluster from that registry.</span></span>

### <a name="create-an-acr-instance"></a><span data-ttu-id="93ece-181">Tworzenie wystąpienia ACR</span><span class="sxs-lookup"><span data-stu-id="93ece-181">Create an ACR instance</span></span>

<span data-ttu-id="93ece-182">Uruchom następujące polecenie w **interfejsie AZ CLI** :</span><span class="sxs-lookup"><span data-stu-id="93ece-182">Run the following command from the **az cli** :</span></span>

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> <span data-ttu-id="93ece-183">Nazwa rejestru kontenerów (np `exploredocker` .) musi być unikatowa w obrębie platformy Azure i zawierać 5-50 znaków alfanumerycznych.</span><span class="sxs-lookup"><span data-stu-id="93ece-183">The container registry name (e.g `exploredocker`) must be unique within Azure, and contain 5-50 alphanumeric characters.</span></span> <span data-ttu-id="93ece-184">Aby uzyskać więcej informacji, zobacz [Tworzenie rejestru kontenerów](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span><span class="sxs-lookup"><span data-stu-id="93ece-184">For more details, refer [Create a container registry](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="93ece-185">Tworzenie obrazu w trybie wydania</span><span class="sxs-lookup"><span data-stu-id="93ece-185">Create the image in Release mode</span></span>

<span data-ttu-id="93ece-186">Teraz utworzysz obraz w trybie **wersji** (gotowy do produkcji), zmieniając do **wersji** , jak pokazano na rysunku 4-46 i uruchamiając aplikację tak jak wcześniej.</span><span class="sxs-lookup"><span data-stu-id="93ece-186">You'll now create the image in **Release** mode (ready for production) by changing to **Release** , as shown in Figure 4-46, and running the application as you did before.</span></span>

![Opcja paska narzędzi w programie VS do kompilowania w trybie wydania.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

<span data-ttu-id="93ece-188">**Rysunek 4-46**.</span><span class="sxs-lookup"><span data-stu-id="93ece-188">**Figure 4-46**.</span></span> <span data-ttu-id="93ece-189">Wybieranie trybu wydania</span><span class="sxs-lookup"><span data-stu-id="93ece-189">Selecting Release Mode</span></span>

<span data-ttu-id="93ece-190">Jeśli wykonasz `docker images` polecenie, zobaczysz oba utworzone obrazy, jedno dla `debug` ( **dev** ) i inne dla `release` ( **Najnowsza** ) tryb.</span><span class="sxs-lookup"><span data-stu-id="93ece-190">If you execute the `docker images` command, you'll see both images created, one for `debug` ( **dev** ) and the other for `release` ( **latest** ) mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="93ece-191">Utwórz nowy tag dla obrazu</span><span class="sxs-lookup"><span data-stu-id="93ece-191">Create a new Tag for the Image</span></span>

<span data-ttu-id="93ece-192">Każdy obraz kontenera musi być oznaczony `loginServer` nazwą rejestru.</span><span class="sxs-lookup"><span data-stu-id="93ece-192">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="93ece-193">Ten tag jest używany na potrzeby kierowania podczas wypychania obrazów kontenerów do rejestru obrazów.</span><span class="sxs-lookup"><span data-stu-id="93ece-193">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="93ece-194">Można wyświetlić `loginServer` nazwę z Azure Portal, pobierając informacje z Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="93ece-194">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Widok w przeglądarce Nazwa rejestru kontenerów platformy Azure znajduje się w prawym górnym rogu.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

<span data-ttu-id="93ece-196">**Rysunek 4-47**.</span><span class="sxs-lookup"><span data-stu-id="93ece-196">**Figure 4-47**.</span></span> <span data-ttu-id="93ece-197">Wyświetl nazwę rejestru</span><span class="sxs-lookup"><span data-stu-id="93ece-197">View of the name of the Registry</span></span>

<span data-ttu-id="93ece-198">Lub uruchamiając następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="93ece-198">Or by running the following command:</span></span>

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Dane wyjściowe konsoli z powyższego polecenia.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

<span data-ttu-id="93ece-200">**Rysunek 4-48**.</span><span class="sxs-lookup"><span data-stu-id="93ece-200">**Figure 4-48**.</span></span> <span data-ttu-id="93ece-201">Pobierz nazwę rejestru przy użyciu polecenia **AZ CLI**</span><span class="sxs-lookup"><span data-stu-id="93ece-201">Get the name of the registry using **az cli**</span></span>

<span data-ttu-id="93ece-202">W obu przypadkach należy uzyskać nazwę.</span><span class="sxs-lookup"><span data-stu-id="93ece-202">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="93ece-203">W naszym przykładzie `exploredocker.azurecr.io` .</span><span class="sxs-lookup"><span data-stu-id="93ece-203">In our example, `exploredocker.azurecr.io`.</span></span>

<span data-ttu-id="93ece-204">Teraz możesz oznaczyć obraz, pobierając najnowszą wersję obrazu (obraz wersji) za pomocą polecenia:</span><span class="sxs-lookup"><span data-stu-id="93ece-204">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

<span data-ttu-id="93ece-205">Po uruchomieniu `docker tag` polecenia należy wyświetlić listę obrazów za pomocą `docker images` polecenia, a obraz z nowym tagiem.</span><span class="sxs-lookup"><span data-stu-id="93ece-205">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Dane wyjściowe konsoli z polecenia Docker images.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

<span data-ttu-id="93ece-207">**Rysunek 4-49**.</span><span class="sxs-lookup"><span data-stu-id="93ece-207">**Figure 4-49**.</span></span> <span data-ttu-id="93ece-208">Widok obrazów oznakowanych</span><span class="sxs-lookup"><span data-stu-id="93ece-208">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="93ece-209">Wypchnij obraz do usługi Azure ACR</span><span class="sxs-lookup"><span data-stu-id="93ece-209">Push the image into the Azure ACR</span></span>

<span data-ttu-id="93ece-210">Zaloguj się do Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="93ece-210">Log in to the Azure Container Registry</span></span>

```console
az acr login --name exploredocker
```

<span data-ttu-id="93ece-211">Wypchnij obraz do usługi Azure ACR za pomocą następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="93ece-211">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push <login-server-name>/<image-name>:v1
```

<span data-ttu-id="93ece-212">To polecenie pobiera obrazy, ale zawiera informacje zwrotne w procesie.</span><span class="sxs-lookup"><span data-stu-id="93ece-212">This command takes a while uploading the images but gives you feedback in the process.</span></span> <span data-ttu-id="93ece-213">Na poniższej ilustracji widać dane wyjściowe z jednego obrazu i inne w toku.</span><span class="sxs-lookup"><span data-stu-id="93ece-213">In the following image, you can see the output from one image completed and another in progress.</span></span>

![Dane wyjściowe konsoli z polecenia Docker push.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

<span data-ttu-id="93ece-215">**Rysunek 4-50**.</span><span class="sxs-lookup"><span data-stu-id="93ece-215">**Figure 4-50**.</span></span> <span data-ttu-id="93ece-216">Dane wyjściowe konsoli z polecenia push.</span><span class="sxs-lookup"><span data-stu-id="93ece-216">Console output from the push command.</span></span>

<span data-ttu-id="93ece-217">Aby wdrożyć aplikację obejmującą wiele kontenerów w klastrze AKS, potrzebne są pewne `.yaml` pliki manifestu, które mają większość właściwości pobieranych z `docker-compose.yml` i `docker-compose.override.yml` plików.</span><span class="sxs-lookup"><span data-stu-id="93ece-217">To deploy your multi-container app into your AKS cluster you need some manifest `.yaml` files that have, most of the properties taken from the `docker-compose.yml` and `docker-compose.override.yml` files.</span></span>

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> <span data-ttu-id="93ece-218">Poprzednie `.yml` pliki włączają tylko te `HTTP` porty, przy użyciu `ASPNETCORE_URLS` parametru, aby uniknąć problemów z brakującym certyfikatem w przykładowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93ece-218">The previous `.yml` files only enable the `HTTP` ports, using the `ASPNETCORE_URLS` parameter, to avoid issues with the missing certificate in the sample app.</span></span>

> [!TIP]
> <span data-ttu-id="93ece-219">Aby dowiedzieć się, jak utworzyć klaster AKS dla tego przykładu, w sekcji [**wdrażanie w usłudze Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) w tym przewodniku.</span><span class="sxs-lookup"><span data-stu-id="93ece-219">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

<span data-ttu-id="93ece-220">Teraz wszystko jest już prawie gotowe do wdrożenia przy użyciu **polecenia kubectl** , ale najpierw należy pobrać poświadczenia z klastra AKS za pomocą tego polecenia:</span><span class="sxs-lookup"><span data-stu-id="93ece-220">Now you're almost ready to deploy using **kubectl** , but first you must get the credentials from the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Dane wyjściowe konsoli z powyższego polecenia: scalono "Eksploruj-Docker-AKS" jako bieżący kontekst w C:\Users\Miguel.kube\config](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

<span data-ttu-id="93ece-222">**Rysunek 4-51**.</span><span class="sxs-lookup"><span data-stu-id="93ece-222">**Figure 4-51**.</span></span> <span data-ttu-id="93ece-223">Pobieranie poświadczeń z AKS do środowiska polecenia kubectl.</span><span class="sxs-lookup"><span data-stu-id="93ece-223">Getting credentials from AKS into the kubectl environment.</span></span>

<span data-ttu-id="93ece-224">Należy również zezwolić klastrowi AKS na ściąganie obrazów z ACR przy użyciu tego polecenia:</span><span class="sxs-lookup"><span data-stu-id="93ece-224">You also have to allow the AKS cluster to pull images from the ACR, using this command:</span></span>

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

<span data-ttu-id="93ece-225">Poprzednie polecenie może potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="93ece-225">The previous command might take a couple of minutes to complete.</span></span> <span data-ttu-id="93ece-226">Następnie użyj polecenia, `kubectl apply` Aby uruchomić wdrożenia, a następnie `kubectl get all` Pobierz listę obiektów klastra.</span><span class="sxs-lookup"><span data-stu-id="93ece-226">Then, use the `kubectl apply` command to launch the deployments, and then `kubectl get all` get list the cluster objects.</span></span>

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Dane wyjściowe konsoli z powyższych poleceń: zastosowane wdrożenia.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

<span data-ttu-id="93ece-229">**Rysunek 4-52**.</span><span class="sxs-lookup"><span data-stu-id="93ece-229">**Figure 4-52**.</span></span> <span data-ttu-id="93ece-230">Wdrożenie do Kubernetes</span><span class="sxs-lookup"><span data-stu-id="93ece-230">Deployment to Kubernetes</span></span>

<span data-ttu-id="93ece-231">Zanim moduł równoważenia obciążenia uzyska zewnętrzny adres IP, należy poczekać, `kubectl get services` a następnie aplikacja powinna być dostępna pod tym adresem, jak pokazano na następnym obrazie:</span><span class="sxs-lookup"><span data-stu-id="93ece-231">You'll have to wait a while until the load balancer gets the external IP, checking with `kubectl get services`, and then the application should be available at that address, as shown in the next image:</span></span>

![Widok przeglądarki aplikacji wdrożonej do AKS](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

<span data-ttu-id="93ece-233">**Rysunek 4-53**.</span><span class="sxs-lookup"><span data-stu-id="93ece-233">**Figure 4-53**.</span></span> <span data-ttu-id="93ece-234">Wdrożenie do Kubernetes</span><span class="sxs-lookup"><span data-stu-id="93ece-234">Deployment to Kubernetes</span></span>

<span data-ttu-id="93ece-235">Po zakończeniu wdrażania można uzyskać dostęp do [interfejsu użytkownika sieci Web Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) z lokalnym serwerem proxy przy użyciu tunelu SSH.</span><span class="sxs-lookup"><span data-stu-id="93ece-235">When the deployment completes, you can access the [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) with a local proxy, using an ssh tunnel.</span></span>

<span data-ttu-id="93ece-236">Najpierw należy utworzyć ClusterRoleBinding za pomocą następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="93ece-236">First you must create a ClusterRoleBinding with the following command:</span></span>

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

<span data-ttu-id="93ece-237">A następnie to polecenie, aby uruchomić serwer proxy:</span><span class="sxs-lookup"><span data-stu-id="93ece-237">And then this command to start the proxy:</span></span>

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

<span data-ttu-id="93ece-238">Okno przeglądarki powinno mieć otwarty w `http://127.0.0.1:8001` widoku podobnym do tego:</span><span class="sxs-lookup"><span data-stu-id="93ece-238">A browser window should open at `http://127.0.0.1:8001` with a view similar to this one:</span></span>

![Widok przeglądarki pulpitu nawigacyjnego Kubernetes, przedstawiający wdrożenia, zbiory, zestawy replik i usługi.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

<span data-ttu-id="93ece-240">**Rysunek 4-54**.</span><span class="sxs-lookup"><span data-stu-id="93ece-240">**Figure 4-54**.</span></span> <span data-ttu-id="93ece-241">Wyświetlanie informacji o klastrze Kubernetes</span><span class="sxs-lookup"><span data-stu-id="93ece-241">View Kubernetes cluster information</span></span>

<span data-ttu-id="93ece-242">Teraz masz aplikację ASP.NET Core, działającą w kontenerach systemu Linux i wdrożoną w klastrze AKS na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="93ece-242">Now you have your ASP.NET Core application, running in Linux containers, and deployed to an AKS cluster on Azure.</span></span>

> [!NOTE]
> <span data-ttu-id="93ece-243">Aby uzyskać więcej informacji na temat wdrażania przy użyciu usługi Kubernetes, zobacz: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="93ece-243">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="93ece-244">[Poprzedni](set-up-windows-containers-with-powershell.md) 
>  [Dalej](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="93ece-244">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
