---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507107"
---

### <a name="install-the-sdk"></a>Instalacja zestawu SDK

Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET. W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego. Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Instalowanie środowiska uruchomieniowego

Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego. Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET. W terminalu uruchom następujące polecenia:

```bash
sudo yum install aspnetcore-runtime-5.0
```

Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `aspnetcore-runtime-5.0` w poprzednim poleceniu `dotnet-runtime-5.0` :

```bash
sudo yum install dotnet-runtime-5.0
```
