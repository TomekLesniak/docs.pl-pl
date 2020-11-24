---
title: Docker-gRPC dla deweloperów WCF
description: Tworzenie obrazów platformy Docker dla ASP.NET Core aplikacji gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 0a680d0918868829042e521506fa8c1a1628bf5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688448"
---
# <a name="create-docker-images"></a>Tworzenie obrazów platformy Docker

W tej sekcji opisano tworzenie obrazów platformy Docker dla ASP.NET Core aplikacji gRPC, gotowych do uruchamiania w środowiskach Docker, Kubernetes i innych kontenerach. Przykładowa aplikacja używana z aplikacją sieci Web ASP.NET Core MVC i usługą gRPC jest dostępna w repozytorium [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) w witrynie GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Obrazy podstawowe firmy Microsoft dla aplikacji ASP.NET Core

Firma Microsoft udostępnia wiele podstawowych obrazów do kompilowania i uruchamiania aplikacji platformy .NET Core. Aby utworzyć obraz ASP.NET Core 3,0, należy użyć dwóch obrazów podstawowych:

- Obraz zestawu SDK do kompilowania i publikowania aplikacji.
- Obraz środowiska uruchomieniowego na potrzeby wdrożenia.

| Obraz | Opis |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/) | Do kompilowania aplikacji za pomocą programu `docker build` . Nie do użycia w środowisku produkcyjnym. |
| [mcr.microsoft.com/dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | Zawiera zależności środowiska uruchomieniowego i ASP.NET Core. Dla środowiska produkcyjnego. |

Dla każdego obrazu istnieją cztery warianty oparte na różnych dystrybucjach systemu Linux, które różnią się od tagów.

| Tagi obrazu | Linux | Uwagi |
| --------- | ----- | ----- |
| 3,0 – Buster, 3,0 | Debian 10 | Obraz domyślny, jeśli nie określono żadnego wariantu systemu operacyjnego. |
| 3,0 — Alpine | Alpine 3,9 | Obrazy Alpine Base są znacznie mniejsze niż Debian lub Ubuntu. |
| 3,0 – Disco | Ubuntu 19.04 | |
| 3,0 – Bionic | Ubuntu 18.04 | |

Obraz Alpine Base ma około 100 MB, w porównaniu do 200 MB dla obrazów Debian i Ubuntu. Niektóre pakiety lub biblioteki oprogramowania mogą nie być dostępne w zarządzaniu pakietami Alpine. Jeśli nie masz pewności, którego obrazu użyć, prawdopodobnie wybierz domyślną debian.

> [!IMPORTANT]
> Upewnij się, że używasz tego samego wariantu systemu Linux do kompilowania i środowiska uruchomieniowego. Aplikacje skompilowane i opublikowane na jednym z wariantów mogą nie zadziałały na innym.

## <a name="create-a-docker-image"></a>Tworzenie obrazu platformy Docker

Obraz platformy Docker jest definiowany przez *pliku dockerfile*. Jest to plik tekstowy, który zawiera wszystkie polecenia potrzebne do skompilowania aplikacji i zainstalowania wszelkich zależności, które są wymagane do kompilowania lub uruchamiania aplikacji. Poniższy przykład pokazuje najprostszą pliku dockerfile dla aplikacji ASP.NET Core 3,0:

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Pliku dockerfile ma dwie części: pierwszy z nich używa `sdk` obrazu podstawowego do kompilowania i publikowania aplikacji. drugi tworzy obraz środowiska uruchomieniowego z `aspnet` bazy. Jest to spowodowane tym, że `sdk` obraz jest około 900 MB, w porównaniu do około 200 MB dla obrazu środowiska uruchomieniowego, a większość jego zawartości jest niepotrzebna w czasie wykonywania.

### <a name="the-build-steps"></a>Kroki kompilacji

| Krok | Opis |
| ---- | ----------- |
| `FROM ...` | Deklaruje podstawowy obraz i przypisuje `builder` alias. |
| `WORKDIR /src` | Tworzy `/src` katalog i ustawia go jako bieżący katalog roboczy. |
| `COPY . .` | Kopiuje wszystkie elementy znajdujące się poniżej bieżącego katalogu na hoście do bieżącego katalogu na obrazie. |
| `RUN dotnet restore` | Przywraca wszystkie pakiety zewnętrzne (ASP.NET Core 3,0 Framework jest wstępnie zainstalowany wraz z zestawem SDK). |
| `RUN dotnet publish ...` | Kompiluje i publikuje kompilację wydania. Należy zauważyć, że `--runtime` flaga nie jest wymagana. |

### <a name="the-runtime-image-steps"></a>Kroki obrazu środowiska uruchomieniowego

| Krok | Opis |
| ---- | ----------- |
| `FROM ...` | Deklaruje nowy obraz podstawowy. |
| `WORKDIR /app` | Tworzy `/app` katalog i ustawia go jako bieżący katalog roboczy. |
| `COPY --from=builder ...` | Kopiuje opublikowaną aplikację z poprzedniego obrazu przy użyciu `builder` aliasu z pierwszego `FROM` wiersza. |
| `ENTRYPOINT [ ... ]` | Ustawia polecenie, które ma być uruchamiane po rozpoczęciu kontenera. `dotnet`Polecenie w obrazie środowiska uruchomieniowego może uruchamiać tylko pliki dll. |

### <a name="https-in-docker"></a>HTTPS w Docker

Obrazy podstawowe firmy Microsoft dla platformy Docker ustawiają `ASPNETCORE_URLS` zmienną środowiskową `http://+:80` , co oznacza, że Kestrel działa bez protokołu HTTPS na tym porcie. Jeśli używasz protokołu HTTPS z certyfikatem niestandardowym (zgodnie z opisem w temacie [samodzielnych aplikacji gRPC](self-hosted.md)), należy to zmienić. Ustaw zmienną środowiskową w części Tworzenie obrazu środowiska uruchomieniowego pliku dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Plik. dockerignore

Podobnie jak `.gitignore` pliki, które wykluczają pewne pliki i katalogi z kontroli źródła, `.dockerignore` można użyć pliku do wykluczenia plików i katalogów z kopiowania do obrazu podczas kompilacji. To nie tylko zapisuje kopiowanie czasu, ale można również uniknąć niektórych błędów, które wynikają z tego, że `obj` katalog z komputera jest kopiowany do obrazu. Należy dodać wpisy dla `bin` i `obj` do `.dockerignore` pliku.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Tworzenie obrazu

W przypadku rozwiązania z jedną aplikacją, a tym samym pliku dockerfile, najprostszą jest umieszczenie pliku dockerfile w katalogu podstawowym. Innymi słowy, umieść je w tym samym katalogu, w którym znajduje się `.sln` plik. W takim przypadku, aby skompilować obraz, użyj następującego `docker build` polecenia w katalogu zawierającym pliku dockerfile.

```console
docker build --tag stockdata .
```

Flaga o niewłaściwej nazwie `--tag` (którą można skrócić do `-t` ) określa pełną nazwę obrazu, w tym rzeczywisty tag, jeśli został określony. `.`Na końcu określa kontekst, w którym kompilacja zostanie uruchomiona; bieżący katalog roboczy dla `COPY` poleceń w pliku dockerfile.

Jeśli masz wiele aplikacji w ramach jednego rozwiązania, możesz zachować pliku dockerfile dla każdej aplikacji w swoim folderze, obok `.csproj` pliku. Nadal powinno być uruchamiane `docker build` polecenie z katalogu podstawowego, aby upewnić się, że rozwiązanie i wszystkie projekty są kopiowane do obrazu. Można określić pliku dockerfile poniżej bieżącego katalogu przy użyciu `--file` flagi (lub `-f` ).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Uruchamianie obrazu w kontenerze na maszynie

Aby uruchomić obraz w lokalnym wystąpieniu platformy Docker, użyj `docker run` polecenia.

```console
docker run -ti -p 5000:80 stockdata
```

`-ti`Flaga łączy bieżący terminal z terminalem kontenera i działa w trybie interaktywnym. `-p 5000:80`Port "publishs" (linki) 80 w kontenerze do portu 5000 w interfejsie sieciowym hosta lokalnego.

## <a name="push-the-image-to-a-registry"></a>Wypchnij obraz do rejestru

Po zweryfikowaniu, że obraz działa, wypchnij go do rejestru platformy Docker, aby udostępnić go w innych systemach. Sieci wewnętrzne muszą obsługiwać rejestr platformy Docker. Może to być tak proste jak uruchamianie [własnego `registry` obrazu platformy Docker](https://docs.docker.com/registry/deploying/) (rejestr platformy Docker jest uruchamiany w kontenerze platformy Docker), ale dostępne są różne bardziej kompleksowe rozwiązania. W przypadku udostępniania zewnętrznego i używania w chmurze dostępne są różne rejestry zarządzane, takie jak [Azure Container Registry](/azure/container-registry/) lub usługa [Docker Hub](https://docs.docker.com/docker-hub/repos/).

Aby przeprowadzić wypychanie do centrum platformy Docker, poprzedź nazwę obrazu nazwą użytkownika lub organizacji.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Aby wypchnąć do rejestru prywatnego, prefiks nazwy obrazu z nazwą hosta rejestru i nazwą organizacji.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Gdy obraz znajduje się w rejestrze, można wdrożyć go na poszczególnych hostach platformy Docker lub w aparacie aranżacji kontenera, takim jak Kubernetes.

>[!div class="step-by-step"]
>[Poprzedni](self-hosted.md) 
> [Dalej](kubernetes.md)
