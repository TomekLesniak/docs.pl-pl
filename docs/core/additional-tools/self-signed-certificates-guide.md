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
# <a name="generate-self-signed-certificates-with-the-net-cli"></a>Generowanie certyfikatów z podpisem własnym za pomocą interfejsu wiersza polecenia platformy .NET

W przypadku korzystania z certyfikatów z podpisem własnym istnieją różne sposoby tworzenia i używania ich na potrzeby scenariuszy tworzenia i testowania.  W tym przewodniku omówiono korzystanie z certyfikatów z podpisem własnym `dotnet dev-certs` i innych opcji, takich jak `PowerShell` i `OpenSSL` .

Następnie można sprawdzić, czy certyfikat zostanie załadowany przy użyciu przykładu, takiego jak [aplikacja ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hostowana w kontenerze.

## <a name="prerequisites"></a>Wymagania wstępne

W przykładzie można użyć platformy .NET Core 3,1 lub .NET 5.

W przypadku programu `dotnet dev-certs` upewnij się, że zainstalowano odpowiednią wersję programu .NET:

* [Instalowanie programu .NET w systemie Windows](../install/windows.md)
* [Instalowanie programu .NET w systemie Linux](../install/linux.md)
* [Zainstaluj platformę .NET na macOS](../install/macos.md)

Ten przykład wymaga [platformy docker 17,06](https://docs.docker.com/release-notes/docker-ce) lub nowszej wersji [klienta platformy Docker](https://www.docker.com/products/docker).

## <a name="prepare-sample-app"></a>Przygotowanie przykładowej aplikacji

Należy przygotować przykładową aplikację w zależności od środowiska uruchomieniowego, którego chcesz użyć do testowania, [.NET Core 3,1](#net-core-31-sample-app) lub [.NET 5](#net-5-sample-app).

W tym przewodniku użyjesz [przykładowej aplikacji](https://hub.docker.com/_/microsoft-dotnet-samples) i wprowadzisz zmiany w odpowiednim miejscu.

### <a name="net-core-31-sample-app"></a>Przykładowa aplikacja platformy .NET Core 3,1

Pobieranie przykładowej aplikacji.

```console
git clone https://github.com/dotnet/dotnet-docker/
```

Przejdź lokalnie do repozytorium i Otwórz obszar roboczy w edytorze.

> [!NOTE]
> Aby *obciąć* wdrożenie przy użyciu parametrów dotnet Publish, należy upewnić się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.
Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze. Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.

Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

Zmodyfikuj pliku dockerfile, aby upewnić się, że środowisko uruchomieniowe wskazuje na platformę .NET Core 3,1:

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

Upewnij się, że wskażesz przykładową aplikację.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Utwórz kontener do testowania lokalnego.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a>Przykładowa aplikacja platformy .NET 5

W tym przewodniku [Przykładowa aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) powinna zostać sprawdzona dla programu .NET 5.

Sprawdź, czy aplikacja Przykładowa [pliku dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) korzysta z platformy .NET 5.

W zależności od systemu operacyjnego hosta może być konieczne zaktualizowanie środowiska uruchomieniowego ASP.NET. Na przykład zmiana z `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` na na `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` pliku dockerfile będzie pomocna w odniesieniu do odpowiedniego środowiska uruchomieniowego systemu Windows.

Na przykład może to pomóc w testowaniu certyfikatów w systemie Windows:

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

Jeśli testujesz certyfikaty w systemie Linux, możesz użyć istniejącej pliku dockerfile.

Upewnij się, że `aspnetapp.csproj` zawiera ona odpowiednią platformę docelową:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> Jeśli chcesz użyć `dotnet publish` parametrów do *przycinania* wdrożenia, upewnij się, że odpowiednie zależności są dołączone do obsługi certyfikatów SSL.
Zaktualizuj [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) , aby upewnić się, że odpowiednie zestawy znajdują się w kontenerze. Aby uzyskać informacje, należy sprawdzić, jak zaktualizować plik. csproj, aby [obsługiwał certyfikaty SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) podczas korzystania z przycinania do wdrożeń samodzielnych.

Upewnij się, że wskażesz przykładową aplikację.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Utwórz kontener do testowania lokalnego.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a>Tworzenie certyfikatu z podpisem własnym

Można utworzyć certyfikat z podpisem własnym:

- [Przy użyciu programu dotnet dev-certs](#with-dotnet-dev-certs)
- [Z programem PowerShell](#with-powershell)
- [Z OpenSSL](#with-openssl)

### <a name="with-dotnet-dev-certs"></a>Przy użyciu programu dotnet dev-certs

Programu można użyć `dotnet dev-certs` do pracy z certyfikatami z podpisem własnym. W tym przykładzie używa się konsoli programu PowerShell.

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> Nazwa certyfikatu, w tym przypadku *aspnetapp*. pfx musi być zgodna z nazwą zestawu projektu. `crypticpassword` jest używany jako autonomiczny dla hasła wybieranego przez użytkownika. Jeśli konsola zwróci wartość "prawidłowy certyfikat HTTPS jest już obecny", zaufany certyfikat już istnieje w magazynie. Można go wyeksportować przy użyciu konsoli programu MMC.

Skonfiguruj wpisy tajne aplikacji dla certyfikatu:

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> Uwaga: hasło musi być zgodne z hasłem użytym dla certyfikatu.

Uruchom obraz kontenera z ASP.NET Core skonfigurowanym dla protokołu HTTPS:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

Po uruchomieniu aplikacji przejdź do `https://localhost:8001` przeglądarki sieci Web.

#### <a name="clean-up"></a>Czyszczenie

Jeśli wpisy tajne i certyfikaty nie są używane, należy je wyczyścić.

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a>Z programem PowerShell

Za pomocą programu PowerShell można generować certyfikaty z podpisem własnym. [Klienta PKI](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) można użyć do wygenerowania certyfikatu z podpisem własnym.

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

Certyfikat zostanie wygenerowany, ale na potrzeby testowania należy umieścić go w magazynie certyfikatów do testowania w przeglądarce.

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

W tym momencie certyfikaty powinny być widoczne w [przystawce programu MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).

Przykładowy kontener można uruchomić w podsystemie Windows dla systemu Linux (WSL):

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> Należy pamiętać, że w przypadku instalacji woluminu ścieżka pliku może być obsługiwana inaczej w zależności od hosta.  Na przykład w programie WSL może zamienić */c/certs* na */mnt/c/certs*.

Jeśli używasz kontenera skompilowanego wcześniej dla systemu Windows, polecenie Uruchom będzie wyglądać następująco:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.

Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1). Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .

#### <a name="clean-up"></a>Czyszczenie

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a>Z OpenSSL

Za pomocą [OpenSSL](https://www.openssl.org/) można tworzyć certyfikaty z podpisem własnym. W tym przykładzie użyto WSL/Ubuntu i powłoki bash z `OpenSSL` .

Spowoduje to wygenerowanie klucza. CRT i.

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

Aby uzyskać plik PFX, użyj następującego polecenia:

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> Przykład. aspnetcore 3,1 użyje `.pfx` i hasła. Począwszy od `.net 5` środowiska uruchomieniowego, Kestrel może również przyjmować `.crt` pliki kodowane przez PEM `.key` .

W zależności od systemu operacyjnego hosta certyfikat musi być zaufany. Na hoście z systemem Linux "Ufaj" certyfikat jest inny i dystrybucji zależny.

Na potrzeby tego przewodnika przedstawiono przykład w systemie Windows przy użyciu programu PowerShell:

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

W przypadku platformy .NET Core 3,1 Uruchom następujące polecenie w WSL:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

Począwszy od platformy .NET 5, Kestrel może przyjmować `.crt` pliki z kodowaniem PEM `.key` . Można uruchomić przykład za pomocą następującego polecenia dla programu .NET 5:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> Należy pamiętać, że w programie WSL ścieżka instalacji woluminu może ulec zmianie w zależności od konfiguracji.

W przypadku platformy .NET Core 3,1 w systemie Windows uruchom następujące polecenie w `Powershell` :

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

W przypadku platformy .NET 5 w systemie Windows uruchom następujące polecenie w programie PowerShell:

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

Po uruchomieniu aplikacji przejdź do contoso.com:8001 w przeglądarce.

Upewnij się, że wpisy hosta zostały zaktualizowane pod kątem `contoso.com` odpowiedzi na odpowiedni adres IP (na przykład 127.0.0.1). Jeśli certyfikat nie jest rozpoznawany, upewnij się, że certyfikat załadowany z kontenerem jest również zaufany na hoście oraz że odpowiednie wpisy dotyczące sieci SAN/DNS są dostępne dla programu `contoso.com` .

#### <a name="clean-up"></a>Czyszczenie

Pamiętaj, aby wyczyścić certyfikaty z podpisem własnym po zakończeniu testowania.

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
