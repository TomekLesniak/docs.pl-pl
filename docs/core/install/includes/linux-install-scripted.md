---
ms.openlocfilehash: 540eebd957ce8ce0928db2bd8317cb220cba30bb
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031774"
---

[Skrypty dotnet-Install](../../tools/dotnet-install-script.md) są używane na potrzeby automatyzacji i nieadministracyjnych instalacji **zestawu SDK** i **środowiska uruchomieniowego**. Skrypt można pobrać z programu <https://dot.net/v1/dotnet-install.sh> .

Skrypt domyślnie instaluje najnowszą wersję programu [obsługi długoterminowej (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) zestawu SDK, która jest .net Core 3,1. Aby zainstalować bieżącą wersję, która nie może być wersją (LTS), użyj `-c Current` parametru.

```bash
./dotnet-install.sh -c Current
```

Aby zainstalować środowisko uruchomieniowe platformy .NET zamiast zestawu SDK, użyj `--runtime` parametru.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Określoną wersję można zainstalować, zmieniając `-c` parametr w celu wskazania określonej wersji. Następujące polecenie instaluje zestaw SDK programu .NET 5,0.

```bash
./dotnet-install.sh -c 5.0
```

Aby uzyskać więcej informacji, zobacz temat informacje o [skryptach dotnet-Install](../../tools/dotnet-install-script.md).
