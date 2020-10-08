---
title: Kompiluj ASP.NET Core aplikacje wdrożone jako kontenery systemu Linux w klastrach AKS/Kubernetes
description: Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 8b3141d79eeb252ec3721d57293bed0e335b41d3
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844566"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Kompiluj ASP.NET Core aplikacje wdrożone jako kontenery systemu Linux w programie Orchestrator AKS/Kubernetes

Usługa Azure Kubernetes Services (AKS) to zarządzane przez platformę Azure usługi, które upraszczają wdrażanie kontenerów i zarządzanie nimi.

Główne funkcje AKS są następujące:

- Oparta na platformie Azure płaszczyzna kontroli
- Automatyczne uaktualnienia
- Samonaprawianie
- Skalowanie konfigurowalne przez użytkownika
- Prostsze środowisko użytkownika dla deweloperów i operatorów klastrów.

W poniższych przykładach pokazano, jak utworzyć aplikację ASP.NET Core 3,1 działającą w systemie Linux i wdrożyć ją w klastrze AKS na platformie Azure, podczas gdy programowanie odbywa się przy użyciu programu Visual Studio 2019.

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a>Tworzenie projektu ASP.NET Core przy użyciu programu Visual Studio 2019

ASP.NET Core jest platformą programistyczną ogólnego przeznaczenia obsługiwaną przez firmę Microsoft i społeczność programu .NET w witrynie GitHub. Jest to międzyplatformowe, pomocnicze systemy Windows, macOS i Linux oraz mogą być używane w scenariuszach urządzeń, chmur i osadzonych/IoT.

Ten przykład korzysta z kilku prostych projektów opartych na szablonach programu Visual Studio, więc nie potrzebujesz więcej informacji na temat tworzenia przykładu. Wystarczy utworzyć projekt przy użyciu standardowego szablonu, który zawiera wszystkie elementy, aby uruchomić niewielki projekt z interfejsem API REST i aplikacją internetową ze stronami Razor przy użyciu technologii ASP.NET Core 3,1.

![Dodaj nowe okno projektu w programie Visual Studio, wybierając ASP.NET Core aplikacji sieci Web.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

**Rysunek 4-35**. Tworzenie aplikacji sieci Web ASP.NET Core w programie Visual Studio 2019.

Aby utworzyć przykładowy projekt w programie Visual Studio, wybierz pozycję **plik**  >  **Nowy**  >  **projekt**, wybierz typ projektu **sieci Web** , a następnie szablon **aplikacji sieci Web ASP.NET Core** . Możesz również wyszukać szablon, jeśli będzie potrzebny.

Następnie wprowadź nazwę i lokalizację aplikacji, jak pokazano na następnym obrazie.

![Wprowadź nazwę projektu i lokalizację.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

**Rysunek 4-36**. Wprowadź nazwę i lokalizację projektu w programie Visual Studio 2019.

Upewnij się, że wybrano ASP.NET Core 3,1 jako strukturę. Program .NET Core 3,1 jest dołączony do najnowszej wersji programu Visual Studio 2019 i jest automatycznie instalowany i konfigurowany podczas instalowania programu Visual Studio.

![Okno dialogowe programu Visual Studio, w którym można wybrać typ aplikacji sieci Web ASP.NET Core przy użyciu opcji API.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

**Rysunek 4-37**. Wybieranie ASP.NET CORE 3,1 i typ projektu interfejsu API sieci Web

Obsługa platformy Docker nie jest teraz włączona, wystarczy ją wyświetlić po utworzeniu projektu.

Jeśli masz poprzednią wersję programu .NET Core, możesz pobrać i zainstalować wersję 3,1 z programu <https://dotnet.microsoft.com/download> .

Aby w dowolnym momencie można było wyświetlić projekt "przekształcać", możesz dodać obsługę platformy Docker teraz. Kliknij prawym przyciskiem myszy węzeł projektu w Eksplorator rozwiązań a następnie wybierz polecenie **Dodaj**  >  **obsługę platformy Docker** w menu kontekstowym.

![Opcja menu kontekstowego umożliwiająca dodanie obsługi platformy Docker do istniejącego projektu: kliknij prawym przyciskiem myszy (na projekcie) > Dodaj > obsługa platformy Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

**Rysunek 4-38**. Dodawanie obsługi platformy Docker do istniejącego projektu

Aby ukończyć Dodawanie obsługi platformy Docker, możesz wybrać system Windows lub Linux. W takim przypadku wybierz pozycję **Linux**.

![Opcja okna dialogowego umożliwiającego wybranie docelowego systemu operacyjnego dla pliku dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

**Rysunek 4-39**. Wybieranie kontenerów systemu Linux.

Dzięki tym prostym krokom aplikacja ASP.NET Core 3,1 działa w kontenerze systemu Linux.

W podobny sposób można również dodać bardzo prosty projekt **webapp** (rysunek 4-40) do korzystania z punktu końcowego internetowego interfejsu API, chociaż szczegółowe informacje nie zostały omówione w tym miejscu.

Następnie można dodać obsługę programu Orchestrator dla projektu **WebAPI** , jak pokazano poniżej, w obrazie 4-40.

![Dodawanie obsługi programu Orchestrator do projektu WebApi](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

**Rysunek 4-40**. Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .

Po wybraniu `Docker Compose` opcji, która jest precyzyjna dla rozwoju lokalnego, program Visual Studio dodaje projekt Docker-Zredaguj z plikami z systemem Docker, jak pokazano w obrazie 4-41.

![Docker — tworzenie i dodawanie do rozwiązania](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

**Rysunek 4-41**. Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .

Pliki początkowe dodane są podobne do następujących:

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

Aby aplikacja była uruchamiana z Docker Compose wystarczy tylko wprowadzić kilka dostosowań `docker-compose.override.yml`

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

Teraz możesz uruchomić aplikację przy użyciu klawisza **F5** lub przy użyciu przycisku **Odtwórz** lub klawisza **Ctrl + F5** , wybierając projekt Docker-zredaguj, jak pokazano na ilustracji 4-42.

![Uruchamianie platformy Docker — redagowanie projektu w programie Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

**Rysunek 4-42**. Dodawanie obsługi programu Orchestrator do projektu *WebAPI* .

W przypadku uruchamiania aplikacji platformy Docker, jak wyjaśniono, uzyskasz następujące korzyści:

1. Skompilowane obrazy i kontenery utworzone zgodnie z plikiem dla platformy Docker.
2. Przeglądarka jest otwarta w adresie skonfigurowanym w oknie dialogowym "właściwości" dla `docker-compose` projektu.
3. Otwarte okno **kontenera** (w programie Visual Studio 2019 w wersji 16,4 lub nowszej).
4. Obsługa debugera dla wszystkich projektów w rozwiązaniu, jak pokazano na poniższych ilustracjach.

Otwarto przeglądarkę:

![Widok przeglądarki z uruchomioną aplikacją sieci Web](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

**Rysunek 4-43**. Okno przeglądarki z aplikacją uruchomioną w wielu kontenerach.

Okno kontenerów:

![Okno "kontenery" programu Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

**Rysunek 4-44**. Okno "kontenery" programu Visual Studio

Okno **kontenerów** pozwala wyświetlić uruchomione kontenery, przeglądać dostępne obrazy, wyświetlać zmienne środowiskowe, dzienniki i mapowania portów, sprawdzać system plików, dołączać debuger lub otwierać okno terminalu w środowisku kontenera.

Jak widać, integracja między programem Visual Studio 2019 i platformą Docker jest całkowicie ukierunkowana na produktywność dewelopera.

Oczywiście można również wyświetlić listę obrazów przy użyciu `docker images` polecenia. Powinny być widoczne `webapi` obrazy i `webapp` z `dev` tagami utworzonymi przez automatyczne wdrażanie naszego projektu przy użyciu programu Visual Studio 2019.

```console
docker images
```

![Dane wyjściowe konsoli z polecenia Docker images, wyświetla listę z: Repository, tag, Image ID, Created (Date) i size.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

**Rysunek 4-45**. Widok obrazów platformy Docker

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a>Zarejestruj rozwiązanie w Azure Container Registry (ACR)

Można przekazać obrazy do [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), ale można również użyć usługi Docker Hub lub innego rejestru, dzięki czemu obrazy można wdrożyć w klastrze AKS z tego rejestru.

### <a name="create-an-acr-instance"></a>Tworzenie wystąpienia ACR

Uruchom następujące polecenie w **interfejsie AZ CLI**:

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> Nazwa rejestru kontenerów (np `exploredocker` .) musi być unikatowa w obrębie platformy Azure i zawierać 5-50 znaków alfanumerycznych. Aby uzyskać więcej informacji, zobacz [Tworzenie rejestru kontenerów](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)

### <a name="create-the-image-in-release-mode"></a>Tworzenie obrazu w trybie wydania

Teraz utworzysz obraz w trybie **wersji** (gotowy do produkcji), zmieniając do **wersji**, jak pokazano na rysunku 4-46 i uruchamiając aplikację tak jak wcześniej.

![Opcja paska narzędzi w programie VS do kompilowania w trybie wydania.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

**Rysunek 4-46**. Wybieranie trybu wydania

Jeśli wykonasz `docker images` polecenie, zobaczysz oba utworzone obrazy, jedno dla `debug` (**dev**) i inne dla `release` (**Najnowsza**) tryb.

### <a name="create-a-new-tag-for-the-image"></a>Utwórz nowy tag dla obrazu

Każdy obraz kontenera musi być oznaczony `loginServer` nazwą rejestru. Ten tag jest używany na potrzeby kierowania podczas wypychania obrazów kontenerów do rejestru obrazów.

Można wyświetlić `loginServer` nazwę z Azure Portal, pobierając informacje z Azure Container Registry

![Widok w przeglądarce Nazwa rejestru kontenerów platformy Azure znajduje się w prawym górnym rogu.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

**Rysunek 4-47**. Wyświetl nazwę rejestru

Lub uruchamiając następujące polecenie:

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Dane wyjściowe konsoli z powyższego polecenia.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

**Rysunek 4-48**. Pobierz nazwę rejestru przy użyciu polecenia **AZ CLI**

W obu przypadkach należy uzyskać nazwę. W naszym przykładzie `exploredocker.azurecr.io` .

Teraz możesz oznaczyć obraz, pobierając najnowszą wersję obrazu (obraz wersji) za pomocą polecenia:

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

Po uruchomieniu `docker tag` polecenia należy wyświetlić listę obrazów za pomocą `docker images` polecenia, a obraz z nowym tagiem.

![Dane wyjściowe konsoli z polecenia Docker images.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

**Rysunek 4-49**. Widok obrazów oznakowanych

### <a name="push-the-image-into-the-azure-acr"></a>Wypchnij obraz do usługi Azure ACR

Zaloguj się do Azure Container Registry

```console
az acr login --name exploredocker
```

Wypchnij obraz do usługi Azure ACR za pomocą następującego polecenia:

```console
docker push <login-server-name>/<image-name>:v1
```

To polecenie pobiera obrazy, ale zawiera informacje zwrotne w procesie. Na poniższej ilustracji widać dane wyjściowe z jednego obrazu i inne w toku.

![Dane wyjściowe konsoli z polecenia Docker push.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

**Rysunek 4-50**. Dane wyjściowe konsoli z polecenia push.

Aby wdrożyć aplikację obejmującą wiele kontenerów w klastrze AKS, potrzebne są pewne `.yaml` pliki manifestu, które mają większość właściwości pobieranych z `docker-compose.yml` i `docker-compose.override.yml` plików.

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
> Poprzednie `.yml` pliki włączają tylko te `HTTP` porty, przy użyciu `ASPNETCORE_URLS` parametru, aby uniknąć problemów z brakującym certyfikatem w przykładowej aplikacji.

> [!TIP]
> Aby dowiedzieć się, jak utworzyć klaster AKS dla tego przykładu, w sekcji [**wdrażanie w usłudze Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) w tym przewodniku.

Teraz wszystko jest już prawie gotowe do wdrożenia przy użyciu **polecenia kubectl**, ale najpierw należy pobrać poświadczenia z klastra AKS za pomocą tego polecenia:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Dane wyjściowe konsoli z powyższego polecenia: scalono "Eksploruj-Docker-AKS" jako bieżący kontekst w C:\Users\Miguel.kube\config](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

**Rysunek 4-51**. Pobieranie poświadczeń z AKS do środowiska polecenia kubectl.

Należy również zezwolić klastrowi AKS na ściąganie obrazów z ACR przy użyciu tego polecenia:

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

Poprzednie polecenie może potrwać kilka minut. Następnie użyj polecenia, `kubectl apply` Aby uruchomić wdrożenia, a następnie `kubectl get all` Pobierz listę obiektów klastra.

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Dane wyjściowe konsoli z powyższych poleceń: zastosowane wdrożenia. utworzone usługi.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

**Rysunek 4-52**. Wdrożenie do Kubernetes

Zanim moduł równoważenia obciążenia uzyska zewnętrzny adres IP, należy poczekać, `kubectl get services` a następnie aplikacja powinna być dostępna pod tym adresem, jak pokazano na następnym obrazie:

![Widok przeglądarki aplikacji wdrożonej do AKS](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

**Rysunek 4-53**. Wdrożenie do Kubernetes

Po zakończeniu wdrażania można uzyskać dostęp do [interfejsu użytkownika sieci Web Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) z lokalnym serwerem proxy przy użyciu tunelu SSH.

Najpierw należy utworzyć ClusterRoleBinding za pomocą następującego polecenia:

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

A następnie to polecenie, aby uruchomić serwer proxy:

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

Okno przeglądarki powinno mieć otwarty w `http://127.0.0.1:8001` widoku podobnym do tego:

![Widok przeglądarki pulpitu nawigacyjnego Kubernetes, przedstawiający wdrożenia, zbiory, zestawy replik i usługi.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

**Rysunek 4-54**. Wyświetlanie informacji o klastrze Kubernetes

Teraz masz aplikację ASP.NET Core, działającą w kontenerach systemu Linux i wdrożoną w klastrze AKS na platformie Azure.

> [!NOTE]
> Aby uzyskać więcej informacji na temat wdrażania przy użyciu usługi Kubernetes, zobacz: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

> [!div class="step-by-step"]
> [Poprzedni](set-up-windows-containers-with-powershell.md) 
>  [Dalej](../docker-devops-workflow/index.md)
