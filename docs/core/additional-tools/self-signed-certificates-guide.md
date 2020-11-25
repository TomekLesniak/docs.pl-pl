---
title: Generowanie Self-Signed certyfikatów
description: Omówienie narzędzia Microsoft dotnet dev-certs, które dodaje funkcje dla projektów .NET Core i ASP.NET Core oraz inne opcje używania certyfikatów z podpisem własnym.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: b5bf4b719495c2d6ec248e8592367ac452be91c1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032180"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="1a9c4-103">Generowanie certyfikatów z podpisem własnym za pomocą interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="1a9c4-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="1a9c4-104">W przypadku korzystania z certyfikatów z podpisem własnym istnieją różne sposoby tworzenia i używania ich na potrzeby scenariuszy tworzenia i testowania.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-104">When using self-signed certificates, there are different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="1a9c4-105">W tym przewodniku omówiono korzystanie z certyfikatów z podpisem własnym `dotnet dev-certs` i innych opcji, takich jak `PowerShell` i `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="1a9c4-106">Następnie można sprawdzić, czy certyfikat zostanie załadowany przy użyciu przykładu, takiego jak [aplikacja ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hostowana w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a9c4-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="1a9c4-107">Prerequisites</span></span>

<span data-ttu-id="1a9c4-108">W przykładzie można użyć platformy .NET Core 3,1 lub .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-108">In the sample, you can utilize either .NET Core 3.1 or .NET 5.</span></span>

<span data-ttu-id="1a9c4-109">W przypadku programu `dotnet dev-certs` upewnij się, że zainstalowano odpowiednią wersję programu .NET:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-109">For `dotnet dev-certs`, be sure to have the appropriate version of .NET installed:</span></span>

* [<span data-ttu-id="1a9c4-110">Instalowanie programu .NET w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="1a9c4-110">Install .NET on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="1a9c4-111">Instalowanie programu .NET w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="1a9c4-111">Install .NET on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="1a9c4-112">Zainstaluj platformę .NET na macOS</span><span class="sxs-lookup"><span data-stu-id="1a9c4-112">Install .NET on macOS</span></span>](../install/macos.md)

<span data-ttu-id="1a9c4-113">Ten przykład wymaga [platformy docker 17,06](https://docs.docker.com/release-notes/docker-ce) lub nowszej wersji [klienta platformy Docker](https://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="1a9c4-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="1a9c4-114">Przygotowanie przykładowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="1a9c4-114">Prepare sample app</span></span>

<span data-ttu-id="1a9c4-115">Należy przygotować przykładową aplikację w zależności od środowiska uruchomieniowego, którego chcesz użyć do testowania, [.NET Core 3,1](#net-core-31-sample-app) lub [.NET 5](#net-5-sample-app).</span><span class="sxs-lookup"><span data-stu-id="1a9c4-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing, either [.NET Core 3.1](#net-core-31-sample-app) or [.NET 5](#net-5-sample-app).</span></span>

<span data-ttu-id="1a9c4-116">W tym przewodniku użyjesz [przykładowej aplikacji](https://hub.docker.com/_/microsoft-dotnet-samples) i wprowadzisz zmiany w odpowiednim miejscu.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-116">For this guide, you'll use a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="net-core-31-sample-app"></a><span data-ttu-id="1a9c4-117">Przykładowa aplikacja platformy .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="1a9c4-117">.NET Core 3.1 sample app</span></span>

<span data-ttu-id="1a9c4-118">Pobieranie przykładowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="1a9c4-119">Przejdź lokalnie do repozytorium i Otwórz obszar roboczy w edytorze.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="1a9c4-120">Aby *obciąć* wdrożenie przy użyciu parametrów dotnet Publish, należy upewnić się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="1a9c4-121">Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="1a9c4-122">Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="1a9c4-123">Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="1a9c4-124">Zmodyfikuj pliku dockerfile, aby upewnić się, że środowisko uruchomieniowe wskazuje na platformę .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-124">Modify the Dockerfile to make sure the runtime points to .NET Core 3.1:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

<span data-ttu-id="1a9c4-125">Upewnij się, że wskażesz przykładową aplikację.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="1a9c4-126">Utwórz kontener do testowania lokalnego.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a><span data-ttu-id="1a9c4-127">Przykładowa aplikacja platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="1a9c4-127">.NET 5 sample app</span></span>

<span data-ttu-id="1a9c4-128">W tym przewodniku [Przykładowa aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) powinna zostać sprawdzona dla programu .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .NET 5.</span></span>

<span data-ttu-id="1a9c4-129">Sprawdź, czy aplikacja Przykładowa [pliku dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) korzysta z platformy .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .NET 5.</span></span>

<span data-ttu-id="1a9c4-130">W zależności od systemu operacyjnego hosta może być konieczne zaktualizowanie środowiska uruchomieniowego ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-130">Depending on the host OS, the ASP.NET runtime may need to be updated.</span></span> <span data-ttu-id="1a9c4-131">Na przykład zmiana z `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` na na `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` pliku dockerfile będzie pomocna w odniesieniu do odpowiedniego środowiska uruchomieniowego systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="1a9c4-132">Na przykład może to pomóc w testowaniu certyfikatów w systemie Windows:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-132">For example, this will help with testing the certificates on Windows:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

<span data-ttu-id="1a9c4-133">Jeśli testujesz certyfikaty w systemie Linux, możesz użyć istniejącej pliku dockerfile.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="1a9c4-134">Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="1a9c4-135">Jeśli chcesz użyć `dotnet publish` parametrów do *przycinania* wdrożenia, upewnij się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-135">If you want to use `dotnet publish` parameters to *trim* the deployment, make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="1a9c4-136">Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="1a9c4-137">Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="1a9c4-138">Upewnij się, że wskażesz przykładową aplikację.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="1a9c4-139">Utwórz kontener do testowania lokalnego.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="1a9c4-140">Tworzenie certyfikatu z podpisem własnym</span><span class="sxs-lookup"><span data-stu-id="1a9c4-140">Create a self-signed certificate</span></span>

<span data-ttu-id="1a9c4-141">Można utworzyć certyfikat z podpisem własnym:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-141">You can create a self-signed certificate:</span></span>

- [<span data-ttu-id="1a9c4-142">Przy użyciu programu dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="1a9c4-142">With dotnet dev-certs</span></span>](#with-dotnet-dev-certs)
- [<span data-ttu-id="1a9c4-143">Z programem PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a9c4-143">With PowerShell</span></span>](#with-powershell)
- [<span data-ttu-id="1a9c4-144">Z OpenSSL</span><span class="sxs-lookup"><span data-stu-id="1a9c4-144">With OpenSSL</span></span>](#with-openssl)

### <a name="with-dotnet-dev-certs"></a><span data-ttu-id="1a9c4-145">Przy użyciu programu dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="1a9c4-145">With dotnet dev-certs</span></span>

<span data-ttu-id="1a9c4-146">Programu można użyć `dotnet dev-certs` do pracy z certyfikatami z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-146">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="1a9c4-147">W tym przykładzie używa się konsoli programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-147">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="1a9c4-148">Nazwa certyfikatu, w tym przypadku *aspnetapp*. pfx musi być zgodna z nazwą zestawu projektu.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-148">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="1a9c4-149">`crypticpassword` jest używany jako autonomiczny dla hasła wybieranego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-149">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="1a9c4-150">Jeśli konsola zwróci wartość "prawidłowy certyfikat HTTPS jest już obecny", zaufany certyfikat już istnieje w magazynie.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-150">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="1a9c4-151">Można go wyeksportować przy użyciu konsoli programu MMC.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-151">It can be exported using MMC Console.</span></span>

<span data-ttu-id="1a9c4-152">Skonfiguruj wpisy tajne aplikacji dla certyfikatu:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-152">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="1a9c4-153">Uwaga: hasło musi być zgodne z hasłem użytym dla certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-153">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="1a9c4-154">Uruchom obraz kontenera z ASP.NET Core skonfigurowanym dla protokołu HTTPS:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-154">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="1a9c4-155">Po uruchomieniu aplikacji przejdź do `https://localhost:8001` przeglądarki sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-155">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="1a9c4-156">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="1a9c4-156">Clean up</span></span>

<span data-ttu-id="1a9c4-157">Jeśli wpisy tajne i certyfikaty nie są używane, należy je wyczyścić.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-157">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a><span data-ttu-id="1a9c4-158">Z programem PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a9c4-158">With PowerShell</span></span>

<span data-ttu-id="1a9c4-159">Za pomocą programu PowerShell można generować certyfikaty z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-159">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="1a9c4-160">[Klienta PKI](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) można użyć do wygenerowania certyfikatu z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-160">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="1a9c4-161">Certyfikat zostanie wygenerowany, ale na potrzeby testowania należy umieścić go w magazynie certyfikatów do testowania w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-161">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="1a9c4-162">W tym momencie certyfikaty powinny być widoczne w [przystawce programu MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="1a9c4-162">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="1a9c4-163">Przykładowy kontener można uruchomić w podsystemie Windows dla systemu Linux (WSL):</span><span class="sxs-lookup"><span data-stu-id="1a9c4-163">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="1a9c4-164">Należy pamiętać, że w przypadku instalacji woluminu ścieżka pliku może być obsługiwana inaczej w zależności od hosta.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-164">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="1a9c4-165">Na przykład w programie WSL może zamienić */c/certs* na */mnt/c/certs*.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-165">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="1a9c4-166">Jeśli używasz kontenera skompilowanego wcześniej dla systemu Windows, polecenie Uruchom będzie wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-166">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="1a9c4-167">Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-167">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="1a9c4-168">Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="1a9c4-168">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="1a9c4-169">Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-169">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="1a9c4-170">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="1a9c4-170">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a><span data-ttu-id="1a9c4-171">Z OpenSSL</span><span class="sxs-lookup"><span data-stu-id="1a9c4-171">With OpenSSL</span></span>

<span data-ttu-id="1a9c4-172">Za pomocą [OpenSSL](https://www.openssl.org/) można tworzyć certyfikaty z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-172">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="1a9c4-173">W tym przykładzie użyto WSL/Ubuntu i powłoki bash z `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-173">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="1a9c4-174">Spowoduje to wygenerowanie klucza. CRT i.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-174">This will generate a .crt and a .key.</span></span>

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

<span data-ttu-id="1a9c4-175">Aby uzyskać plik PFX, użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-175">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="1a9c4-176">Przykład. aspnetcore 3,1 użyje `.pfx` i hasła.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-176">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="1a9c4-177">Począwszy od `.net 5` środowiska uruchomieniowego, Kestrel może również przyjmować `.crt` pliki kodowane przez PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-177">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="1a9c4-178">W zależności od systemu operacyjnego hosta certyfikat musi być zaufany.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-178">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="1a9c4-179">Na hoście z systemem Linux "Ufaj" certyfikat jest inny i dystrybucji zależny.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-179">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="1a9c4-180">Na potrzeby tego przewodnika przedstawiono przykład w systemie Windows przy użyciu programu PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-180">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="1a9c4-181">W przypadku platformy .NET Core 3,1 Uruchom następujące polecenie w WSL:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-181">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="1a9c4-182">Począwszy od platformy .NET 5, Kestrel może przyjmować `.crt` pliki z kodowaniem PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-182">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="1a9c4-183">Można uruchomić przykład za pomocą następującego polecenia dla programu .NET 5:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-183">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="1a9c4-184">Należy pamiętać, że w programie WSL ścieżka instalacji woluminu może ulec zmianie w zależności od konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-184">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="1a9c4-185">W przypadku platformy .NET Core 3,1 w systemie Windows uruchom następujące polecenie w `Powershell` :</span><span class="sxs-lookup"><span data-stu-id="1a9c4-185">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="1a9c4-186">W przypadku platformy .NET 5 w systemie Windows uruchom następujące polecenie w programie PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1a9c4-186">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="1a9c4-187">Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-187">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="1a9c4-188">Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="1a9c4-188">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="1a9c4-189">Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1a9c4-189">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="1a9c4-190">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="1a9c4-190">Clean up</span></span>

<span data-ttu-id="1a9c4-191">Pamiętaj, aby wyczyścić certyfikaty z podpisem własnym po zakończeniu testowania.</span><span class="sxs-lookup"><span data-stu-id="1a9c4-191">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
