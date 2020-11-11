---
ms.openlocfilehash: ed269683f5c4569c21ae53e9a3c1ec65eb5ebd43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506871"
---

### <a name="install-the-sdk"></a>Instalacja zestawu SDK

Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET. W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego. Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:

```bash
sudo zypper install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Instalowanie środowiska uruchomieniowego

Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego. Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET. W terminalu uruchom następujące polecenia:

```bash
sudo zypper install aspnetcore-runtime-5.0
```

Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `aspnetcore-runtime-5.0` w poprzednim poleceniu `dotnet-runtime-5.0` :

```bash
sudo zypper install dotnet-runtime-5.0
```
