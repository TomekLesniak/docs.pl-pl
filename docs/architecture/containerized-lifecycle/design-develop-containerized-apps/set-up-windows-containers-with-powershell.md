---
title: Używanie poleceń programu Windows PowerShell w pliku DockerFile do konfigurowania kontenerów systemu Windows (opartych na standardzie platformy Docker)
description: Dowiedz się, jak używać programu PowerShell podczas pracy z platformą Docker w kontenerach systemu Windows
ms.date: 08/06/2020
ms.openlocfilehash: d65538c821a848d83915e715ee3a02990b40e836
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681252"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Używanie poleceń programu Windows PowerShell w pliku DockerFile do konfigurowania kontenerów systemu Windows (opartych na standardzie platformy Docker)

[Kontenery systemu Windows](/virtualization/windowscontainers/about/index)umożliwiają konwertowanie istniejących aplikacji systemu Windows na obrazy platformy Docker i wdrażanie ich przy użyciu tych samych narzędzi, co w przypadku reszty ekosystemu platformy Docker.

Aby korzystać z kontenerów systemu Windows, wystarczy napisać polecenia programu Windows PowerShell w pliku dockerfile, jak pokazano w następującym przykładzie:

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

W takim przypadku korzystamy z programu Windows PowerShell, aby zainstalować podstawowy obraz systemu Windows Server Core oraz usługi IIS.

W podobny sposób można również użyć poleceń programu Windows PowerShell, aby skonfigurować dodatkowe składniki, takie jak tradycyjne ASP.NET 4. x i .NET Framework 4,6 lub inne oprogramowanie systemu Windows, jak pokazano poniżej:

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Poprzedni](visual-studio-tools-for-docker.md) 
> [Dalej](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
