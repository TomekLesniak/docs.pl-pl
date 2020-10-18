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
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="c0b92-103">Zmiany w programie MSBuild</span><span class="sxs-lookup"><span data-stu-id="c0b92-103">MSBuild breaking changes</span></span>

<span data-ttu-id="c0b92-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="c0b92-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c0b92-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="c0b92-105">Breaking change</span></span> | <span data-ttu-id="c0b92-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="c0b92-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="c0b92-107">TargetFramework Zmień z netcoreapp na net</span><span class="sxs-lookup"><span data-stu-id="c0b92-107">TargetFramework change from netcoreapp to net</span></span>](#targetframework-change-from-netcoreapp-to-net) | <span data-ttu-id="c0b92-108">5,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-108">5.0</span></span> |
| [<span data-ttu-id="c0b92-109">Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="c0b92-109">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="c0b92-110">5,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-110">5.0</span></span> |
| [<span data-ttu-id="c0b92-111">PublishDepsFilePath zmiana zachowania</span><span class="sxs-lookup"><span data-stu-id="c0b92-111">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="c0b92-112">5,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-112">5.0</span></span> |
| [<span data-ttu-id="c0b92-113">Pliki Directory. Packages. props są importowane domyślnie</span><span class="sxs-lookup"><span data-stu-id="c0b92-113">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="c0b92-114">5,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-114">5.0</span></span> |
| [<span data-ttu-id="c0b92-115">Zmiana nazwy pliku manifestu zasobu</span><span class="sxs-lookup"><span data-stu-id="c0b92-115">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="c0b92-116">3,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-116">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c0b92-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="c0b92-117">.NET 5.0</span></span>

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="c0b92-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c0b92-118">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
