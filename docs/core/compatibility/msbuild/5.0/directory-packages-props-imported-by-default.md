---
title: 'Istotna zmiana: pliki Directory. Packages. props są importowane domyślnie'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, gdzie pliki. props programu NuGet są automatycznie importowane plik o nazwie Directory. Packages. props, jeśli znajduje się w folderze projektu.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761459"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="a24a3-103">Pliki Directory. Packages. props są importowane domyślnie</span><span class="sxs-lookup"><span data-stu-id="a24a3-103">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="a24a3-104">Pliki *. props* programu NuGet automatycznie importują plik o nazwie *Directory. Packages. props* , jeśli znajduje się w folderze projektu lub w dowolnym jego elemencie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="a24a3-104">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a24a3-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a24a3-105">Version introduced</span></span>

<span data-ttu-id="a24a3-106">5,0</span><span class="sxs-lookup"><span data-stu-id="a24a3-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="a24a3-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a24a3-107">Change description</span></span>

<span data-ttu-id="a24a3-108">W poprzednich wersjach programu .NET może istnieć plik o nazwie *Directory. Packages. props* w pliku projektu i nie zostanie on automatycznie zaimportowany przez plik *. props* programu NuGet w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a24a3-108">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="a24a3-109">Począwszy od platformy .NET 5,0, taki plik *jest* automatycznie importowany, jeśli istnieje w folderze projektu lub w dowolnym z jego elementów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="a24a3-109">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="a24a3-110">Jeśli w folderze projektu znajduje się plik o tej nazwie, ten Automatyczny import może zmienić zachowanie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a24a3-110">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="a24a3-111">Na przykład plik zostanie zaimportowany, ale nie był wcześniej lub kolejność, w której zaimportowano, może ulec zmianie, jeśli zostanie zaimportowany.</span><span class="sxs-lookup"><span data-stu-id="a24a3-111">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a24a3-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a24a3-112">Reason for change</span></span>

<span data-ttu-id="a24a3-113">Ta zmiana została wprowadzona w celu obsługi [centralnej wersji pakietu](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) dla programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="a24a3-113">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a24a3-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a24a3-114">Recommended action</span></span>

<span data-ttu-id="a24a3-115">Zmień nazwę istniejącego *katalogu. Packages. props* , jeśli nie powinien być importowany automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a24a3-115">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a24a3-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a24a3-116">Affected APIs</span></span>

<span data-ttu-id="a24a3-117">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="a24a3-117">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
