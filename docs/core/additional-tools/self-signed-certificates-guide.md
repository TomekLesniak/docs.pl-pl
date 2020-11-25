---
title: Generowanie Self-Signed certyfikatów
description: Omówienie narzędzia Microsoft dotnet dev-certs, które dodaje funkcje dla projektów .NET Core i ASP.NET Core oraz inne opcje używania certyfikatów z podpisem własnym.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: 15bbe3997ca34b503074595fa027bc6dfff1c0a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761423"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="b4592-103">Generowanie certyfikatów z podpisem własnym za pomocą interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="b4592-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="b4592-104">W przypadku korzystania z certyfikatów z podpisem własnym istnieją różne sposoby tworzenia i używania ich na potrzeby scenariuszy projektowania i testowania.</span><span class="sxs-lookup"><span data-stu-id="b4592-104">When using self-signed certificates, there's different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="b4592-105">W tym przewodniku omówiono korzystanie z certyfikatów z podpisem własnym `dotnet dev-certs` i innych opcji, takich jak `PowerShell` i `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="b4592-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="b4592-106">Następnie można sprawdzić, czy certyfikat zostanie załadowany przy użyciu przykładu, takiego jak [aplikacja ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hostowana w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="b4592-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4592-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b4592-107">Prerequisites</span></span>

<span data-ttu-id="b4592-108">W przykładzie można użyć albo `.netcore 3.1` `.net 5` .</span><span class="sxs-lookup"><span data-stu-id="b4592-108">In the sample, you can utilize either `.netcore 3.1` or `.net 5`.</span></span>

<span data-ttu-id="b4592-109">W przypadku programu `dotnet dev-certs` upewnij się, że `dotnet` zainstalowano odpowiednią wersję programu:</span><span class="sxs-lookup"><span data-stu-id="b4592-109">For `dotnet dev-certs`, be sure to have the appropriate version of `dotnet` installed:</span></span>

* [<span data-ttu-id="b4592-110">Instalowanie dotnet w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="b4592-110">Install dotnet on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="b4592-111">Instalowanie dotnet w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="b4592-111">Install dotnet on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="b4592-112">Zainstaluj program dotnet w systemie macOS</span><span class="sxs-lookup"><span data-stu-id="b4592-112">Install dotnet on macOS</span></span>](../install/macos.md)

<span data-ttu-id="b4592-113">Ten przykład wymaga [platformy docker 17,06](https://docs.docker.com/release-notes/docker-ce) lub nowszej wersji [klienta platformy Docker](https://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="b4592-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="b4592-114">Przygotowanie przykładowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="b4592-114">Prepare sample app</span></span>

<span data-ttu-id="b4592-115">Należy przygotować przykładową aplikację w zależności od środowiska uruchomieniowego, którego chcesz użyć do testowania.</span><span class="sxs-lookup"><span data-stu-id="b4592-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing.</span></span>

<span data-ttu-id="b4592-116">W tym przewodniku będziesz korzystać z [przykładowej aplikacji](https://hub.docker.com/_/microsoft-dotnet-samples) i wprowadzać zmiany w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="b4592-116">For this guide, you'll be using a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="prepare-net-core-31-sample-app"></a><span data-ttu-id="b4592-117">Przygotowanie przykładowej aplikacji platformy .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="b4592-117">Prepare .NET Core 3.1 sample app</span></span>

<span data-ttu-id="b4592-118">Pobieranie przykładowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b4592-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="b4592-119">Przejdź lokalnie do repozytorium i Otwórz obszar roboczy w edytorze.</span><span class="sxs-lookup"><span data-stu-id="b4592-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="b4592-120">Aby *obciąć* wdrożenie przy użyciu parametrów dotnet Publish, należy upewnić się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.</span><span class="sxs-lookup"><span data-stu-id="b4592-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="b4592-121">Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="b4592-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="b4592-122">Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="b4592-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="b4592-123">Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:</span><span class="sxs-lookup"><span data-stu-id="b4592-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="b4592-124">Zmodyfikuj pliku dockerfile, aby upewnić się, że środowisko uruchomieniowe wskazuje na. rdzeń 3,1:</span><span class="sxs-lookup"><span data-stu-id="b4592-124">Modify the Dockerfile to make sure the runtime points to .netcore 3.1:</span></span>

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

<span data-ttu-id="b4592-125">Upewnij się, że wskażesz przykładową aplikację.</span><span class="sxs-lookup"><span data-stu-id="b4592-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="b4592-126">Utwórz kontener do testowania lokalnego.</span><span class="sxs-lookup"><span data-stu-id="b4592-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="prepare-net-5-sample-app"></a><span data-ttu-id="b4592-127">Przygotowywanie przykładowej aplikacji .NET 5</span><span class="sxs-lookup"><span data-stu-id="b4592-127">Prepare .NET 5 sample app</span></span>

<span data-ttu-id="b4592-128">W tym przewodniku [Przykładowa aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) powinna zostać sprawdzona dla programu .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b4592-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .net 5.</span></span>

<span data-ttu-id="b4592-129">Sprawdź, czy aplikacja Przykładowa [pliku dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) korzysta z platformy .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b4592-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .net 5.</span></span>

<span data-ttu-id="b4592-130">W zależności od systemu operacyjnego hosta może być konieczne zaktualizowanie środowiska uruchomieniowego ASPNET.</span><span class="sxs-lookup"><span data-stu-id="b4592-130">Depending on the host os, the aspnet runtime may need to be updated.</span></span> <span data-ttu-id="b4592-131">Na przykład zmiana z `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` na na `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` pliku dockerfile będzie pomocna w odniesieniu do odpowiedniego środowiska uruchomieniowego systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="b4592-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="b4592-132">Na przykład może to pomóc w testowaniu certyfikatów w systemie Windows:</span><span class="sxs-lookup"><span data-stu-id="b4592-132">For example, this will help with testing the certificates on Windows:</span></span>

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

<span data-ttu-id="b4592-133">Jeśli testujesz certyfikaty w systemie Linux, możesz użyć istniejącej pliku dockerfile.</span><span class="sxs-lookup"><span data-stu-id="b4592-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="b4592-134">Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:</span><span class="sxs-lookup"><span data-stu-id="b4592-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="b4592-135">Aby *obciąć* wdrożenie przy użyciu parametrów dotnet Publish, należy upewnić się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.</span><span class="sxs-lookup"><span data-stu-id="b4592-135">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="b4592-136">Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="b4592-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="b4592-137">Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="b4592-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="b4592-138">Upewnij się, że wskażesz przykładową aplikację.</span><span class="sxs-lookup"><span data-stu-id="b4592-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="b4592-139">Utwórz kontener do testowania lokalnego.</span><span class="sxs-lookup"><span data-stu-id="b4592-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate-with-dotnet-dev-certs"></a><span data-ttu-id="b4592-140">Tworzenie certyfikatu z podpisem własnym przy użyciu programu dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="b4592-140">Create a self-signed certificate with dotnet dev-certs</span></span>

<span data-ttu-id="b4592-141">Programu można użyć `dotnet dev-certs` do pracy z certyfikatami z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="b4592-141">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="b4592-142">W tym przykładzie używa się konsoli programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4592-142">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="b4592-143">Nazwa certyfikatu, w tym przypadku *aspnetapp*. pfx musi być zgodna z nazwą zestawu projektu.</span><span class="sxs-lookup"><span data-stu-id="b4592-143">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="b4592-144">`crypticpassword` jest używany jako autonomiczny dla hasła wybieranego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b4592-144">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="b4592-145">Jeśli konsola zwróci wartość "prawidłowy certyfikat HTTPS jest już obecny", zaufany certyfikat już istnieje w magazynie.</span><span class="sxs-lookup"><span data-stu-id="b4592-145">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="b4592-146">Można go wyeksportować przy użyciu konsoli programu MMC.</span><span class="sxs-lookup"><span data-stu-id="b4592-146">It can be exported using MMC Console.</span></span>

<span data-ttu-id="b4592-147">Skonfiguruj wpisy tajne aplikacji dla certyfikatu:</span><span class="sxs-lookup"><span data-stu-id="b4592-147">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="b4592-148">Uwaga: hasło musi być zgodne z hasłem użytym dla certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b4592-148">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="b4592-149">Uruchom obraz kontenera z ASP.NET Core skonfigurowanym dla protokołu HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b4592-149">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="b4592-150">Po uruchomieniu aplikacji przejdź do `https://localhost:8001` przeglądarki sieci Web.</span><span class="sxs-lookup"><span data-stu-id="b4592-150">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

### <a name="clean-up"></a><span data-ttu-id="b4592-151">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="b4592-151">Clean up</span></span>

<span data-ttu-id="b4592-152">Jeśli wpisy tajne i certyfikaty nie są używane, należy je wyczyścić.</span><span class="sxs-lookup"><span data-stu-id="b4592-152">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

## <a name="create-a-self-signed-certificate-with-powershell"></a><span data-ttu-id="b4592-153">Tworzenie certyfikatu z podpisem własnym przy użyciu programu PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4592-153">Create a self-signed certificate with PowerShell</span></span>

<span data-ttu-id="b4592-154">Za pomocą programu PowerShell można generować certyfikaty z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="b4592-154">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="b4592-155">[Klienta PKI](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) można użyć do wygenerowania certyfikatu z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="b4592-155">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="b4592-156">Certyfikat zostanie wygenerowany, ale na potrzeby testowania należy umieścić go w magazynie certyfikatów do testowania w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="b4592-156">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="b4592-157">W tym momencie certyfikaty powinny być widoczne w [przystawce programu MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="b4592-157">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="b4592-158">Przykładowy kontener można uruchomić w podsystemie Windows dla systemu Linux (WSL):</span><span class="sxs-lookup"><span data-stu-id="b4592-158">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="b4592-159">Należy pamiętać, że w przypadku instalacji woluminu ścieżka pliku może być obsługiwana inaczej w zależności od hosta.</span><span class="sxs-lookup"><span data-stu-id="b4592-159">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="b4592-160">Na przykład w programie WSL może zamienić */c/certs* na */mnt/c/certs*.</span><span class="sxs-lookup"><span data-stu-id="b4592-160">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="b4592-161">Jeśli używasz kontenera skompilowanego wcześniej dla systemu Windows, polecenie Uruchom będzie wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="b4592-161">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="b4592-162">Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="b4592-162">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="b4592-163">Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="b4592-163">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="b4592-164">Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b4592-164">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

### <a name="clean-up"></a><span data-ttu-id="b4592-165">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="b4592-165">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

## <a name="create-a-self-signed-certificate-with-openssl"></a><span data-ttu-id="b4592-166">Tworzenie certyfikatu z podpisem własnym za pomocą OpenSSL</span><span class="sxs-lookup"><span data-stu-id="b4592-166">Create a self-signed certificate with OpenSSL</span></span>

<span data-ttu-id="b4592-167">Za pomocą [OpenSSL](https://www.openssl.org/) można tworzyć certyfikaty z podpisem własnym.</span><span class="sxs-lookup"><span data-stu-id="b4592-167">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="b4592-168">W tym przykładzie użyto WSL/Ubuntu i powłoki bash z `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="b4592-168">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="b4592-169">Spowoduje to wygenerowanie klucza. CRT i.</span><span class="sxs-lookup"><span data-stu-id="b4592-169">This will generate a .crt and a .key.</span></span>

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

<span data-ttu-id="b4592-170">Aby uzyskać plik PFX, użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="b4592-170">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="b4592-171">Przykład. aspnetcore 3,1 użyje `.pfx` i hasła.</span><span class="sxs-lookup"><span data-stu-id="b4592-171">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="b4592-172">Począwszy od `.net 5` środowiska uruchomieniowego, Kestrel może również przyjmować `.crt` pliki kodowane przez PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="b4592-172">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="b4592-173">W zależności od systemu operacyjnego hosta certyfikat musi być zaufany.</span><span class="sxs-lookup"><span data-stu-id="b4592-173">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="b4592-174">Na hoście z systemem Linux "Ufaj" certyfikat jest inny i dystrybucji zależny.</span><span class="sxs-lookup"><span data-stu-id="b4592-174">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="b4592-175">Na potrzeby tego przewodnika przedstawiono przykład w systemie Windows przy użyciu programu PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4592-175">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="b4592-176">W przypadku platformy .NET Core 3,1 Uruchom następujące polecenie w WSL:</span><span class="sxs-lookup"><span data-stu-id="b4592-176">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="b4592-177">Począwszy od platformy .NET 5, Kestrel może przyjmować `.crt` pliki z kodowaniem PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="b4592-177">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="b4592-178">Można uruchomić przykład za pomocą następującego polecenia dla programu .NET 5:</span><span class="sxs-lookup"><span data-stu-id="b4592-178">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="b4592-179">Należy pamiętać, że w programie WSL ścieżka instalacji woluminu może ulec zmianie w zależności od konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b4592-179">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="b4592-180">W przypadku platformy .NET Core 3,1 w systemie Windows uruchom następujące polecenie w `Powershell` :</span><span class="sxs-lookup"><span data-stu-id="b4592-180">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="b4592-181">W przypadku platformy .NET 5 w systemie Windows uruchom następujące polecenie w programie PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4592-181">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="b4592-182">Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="b4592-182">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="b4592-183">Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="b4592-183">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="b4592-184">Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b4592-184">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

### <a name="clean-up"></a><span data-ttu-id="b4592-185">Czyszczenie</span><span class="sxs-lookup"><span data-stu-id="b4592-185">Clean up</span></span>

<span data-ttu-id="b4592-186">Pamiętaj, aby wyczyścić certyfikaty z podpisem własnym po zakończeniu testowania.</span><span class="sxs-lookup"><span data-stu-id="b4592-186">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
