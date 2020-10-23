---
title: Używanie poleceń programu Windows PowerShell w pliku DockerFile do konfigurowania kontenerów systemu Windows (opartych na standardzie platformy Docker)
description: Dowiedz się, jak używać programu PowerShell podczas pracy z platformą Docker w kontenerach systemu Windows
ms.date: 08/06/2020
ms.openlocfilehash: 6096e4cbad4fb37b485d595c650dc10dc5ed5a22
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434813"
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

W podobny sposób można również użyć poleceń programu Windows PowerShell, aby skonfigurować dodatkowe składniki, takie jak tradycyjne ASP.NET 4. x i .NET 4,6 lub inne oprogramowanie systemu Windows, jak pokazano poniżej:

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Poprzedni](visual-studio-tools-for-docker.md) 
> [Dalej](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
