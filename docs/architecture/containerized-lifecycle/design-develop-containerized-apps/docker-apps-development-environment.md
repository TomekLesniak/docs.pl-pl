---
title: Środowisko deweloperskie dla aplikacji platformy Docker
description: Poznaj najważniejsze opcje narzędzia deweloperskiego, które obsługują cykl życia platformy Docker.
ms.date: 08/06/2020
ms.openlocfilehash: 07b42b2bd05ab16ba0fbf61863b050ee2c9e242b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916029"
---
# <a name="development-environment-for-docker-apps"></a>Środowisko deweloperskie dla aplikacji platformy Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opcje narzędzi programistycznych: IDE lub Edytor

Niezależnie od tego, czy wolisz pełną i wydajną platformę IDE, czy też Edytor uproszczony i Agile, firma Microsoft połączyła się z tworzeniem aplikacji platformy Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code i interfejs wiersza polecenia platformy Docker (narzędzia dla wielu platform dla systemów Mac, Linux i Windows)

Jeśli wolisz lekki Edytor Międzyplatformowy obsługujący dowolny język programowania, możesz użyć Visual Studio Code i interfejsu wiersza polecenia platformy Docker. Te produkty zapewniają proste, a jeszcze niezawodne środowisko, które ma kluczowe znaczenie dla usprawnienia przepływu pracy dewelopera. Instalując "Docker for Mac" lub "Docker for Windows" (środowisko programistyczne), deweloperzy platformy Docker mogą używać jednego interfejsu wiersza polecenia platformy Docker do kompilowania aplikacji dla systemu Windows lub Linux (środowisko uruchomieniowe). Dodatkowo Visual Studio Code obsługuje rozszerzenia dla platformy Docker z technologią IntelliSense dla wieloetapowe dockerfile oraz zadania skrótów do uruchamiania poleceń platformy Docker z edytora.

> [!NOTE]
> Aby pobrać Visual Studio Code, przejdź do <https://code.visualstudio.com/download> .
>
> Aby pobrać platformę Docker dla komputerów Mac i Windows, przejdź do <https://www.docker.com/products/docker> .

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio z narzędziami platformy Docker (komputer deweloperski systemu Windows)

Zaleca się używanie programu Visual Studio 2019 z włączonymi wbudowanymi narzędziami platformy Docker. Za pomocą programu Visual Studio można opracowywać, uruchamiać i weryfikować aplikacje bezpośrednio w wybranym środowisku platformy Docker. Naciśnij klawisz F5, aby debugować aplikację (pojedynczy kontener lub wiele kontenerów) bezpośrednio na hoście platformy Docker lub naciśnij klawisze CTRL + F5, aby edytować i odświeżyć aplikację bez konieczności ponownego kompilowania kontenera. Jest to najprostszy i najbardziej zaawansowany wybór dla deweloperów systemu Windows do tworzenia kontenerów platformy Docker dla systemu Linux lub Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio dla komputerów Mac (komputer deweloperski dla komputerów Mac)

Podczas tworzenia aplikacji opartych na platformie Docker można użyć [Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) . Visual Studio dla komputerów Mac oferuje bogatsze środowisko IDE w porównaniu do Visual Studio Code dla komputerów Mac.

## <a name="language-and-framework-choices"></a>Wybór języka i struktury

Aplikacje platformy Docker można opracowywać przy użyciu narzędzi firmy Microsoft z większością nowoczesnych języków. Poniżej znajduje się lista wstępna, ale nie jest ograniczona do niej:

- .NET Core i ASP.NET Core
- Node.js
- Przejdź
- Java
- Ruby
- Python

W zasadzie można użyć dowolnego nowoczesnego języka obsługiwanego przez platformę Docker w systemie Linux lub Windows.

>[!div class="step-by-step"]
>[Poprzedni](deploy-azure-kubernetes-service.md) 
> [Dalej](docker-apps-inner-loop-workflow.md)
