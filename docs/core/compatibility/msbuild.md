---
title: Zmiany w programie MSBuild
description: Wyświetla listę istotnych zmian w programie MSBuild dla platformy .NET Core.
ms.date: 02/10/2020
ms.openlocfilehash: 9b0fba30c8955a6099bde0dc95b4df65a151d9e6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159494"
---
# <a name="msbuild-breaking-changes"></a>Zmiany w programie MSBuild

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [TargetFramework Zmień z netcoreapp na net](#targetframework-change-from-netcoreapp-to-net) | 5,0 |
| [Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | 5,0 |
| [PublishDepsFilePath zmiana zachowania](#publishdepsfilepath-behavior-change) | 5,0 |
| [Pliki Directory. Packages. props są importowane domyślnie](#directorypackagesprops-files-is-imported-by-default) | 5,0 |
| [Zmiana nazwy pliku manifestu zasobu](#resource-manifest-file-name-change) | 3,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
