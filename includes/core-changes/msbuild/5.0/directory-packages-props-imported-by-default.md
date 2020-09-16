---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538825"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="9a0a7-101">Pliki Directory. Packages. props są importowane domyślnie</span><span class="sxs-lookup"><span data-stu-id="9a0a7-101">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="9a0a7-102">Pliki *. props* programu NuGet automatycznie importują plik o nazwie *Directory. Packages. props* , jeśli znajduje się w folderze projektu lub w dowolnym jego elemencie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-102">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9a0a7-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9a0a7-103">Version introduced</span></span>

<span data-ttu-id="9a0a7-104">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="9a0a7-104">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="9a0a7-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9a0a7-105">Change description</span></span>

<span data-ttu-id="9a0a7-106">W poprzednich wersjach programu .NET może istnieć plik o nazwie *Directory. Packages. props* w pliku projektu i nie zostanie on automatycznie zaimportowany przez plik *. props* programu NuGet w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-106">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="9a0a7-107">Począwszy od platformy .NET 5,0, taki plik *jest* automatycznie importowany, jeśli istnieje w folderze projektu lub w dowolnym z jego elementów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-107">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="9a0a7-108">Jeśli w folderze projektu znajduje się plik o tej nazwie, ten Automatyczny import może zmienić zachowanie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-108">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="9a0a7-109">Na przykład plik zostanie zaimportowany, ale nie był wcześniej lub kolejność, w której zaimportowano, może ulec zmianie, jeśli zostanie zaimportowany.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-109">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9a0a7-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="9a0a7-110">Reason for change</span></span>

<span data-ttu-id="9a0a7-111">Ta zmiana została wprowadzona w celu obsługi [centralnej wersji pakietu](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) dla programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-111">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9a0a7-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9a0a7-112">Recommended action</span></span>

<span data-ttu-id="9a0a7-113">Zmień nazwę istniejącego *katalogu. Packages. props* , jeśli nie powinien być importowany automatycznie.</span><span class="sxs-lookup"><span data-stu-id="9a0a7-113">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

#### <a name="category"></a><span data-ttu-id="9a0a7-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9a0a7-114">Category</span></span>

<span data-ttu-id="9a0a7-115">MSBuild</span><span class="sxs-lookup"><span data-stu-id="9a0a7-115">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9a0a7-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9a0a7-116">Affected APIs</span></span>

<span data-ttu-id="9a0a7-117">Brak</span><span class="sxs-lookup"><span data-stu-id="9a0a7-117">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
