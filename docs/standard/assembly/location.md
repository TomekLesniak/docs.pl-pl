---
title: Lokalizacja zestawu
description: Lokalizacja zestawu .NET określa, w jaki sposób środowisko CLR znajduje je i czy może być współużytkowane z innymi zestawami.
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 1fa1c486c0cddce4ddcfae7f2df27e2e85c88e66
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687601"
---
# <a name="assembly-location"></a><span data-ttu-id="f27c0-103">Lokalizacja zestawu</span><span class="sxs-lookup"><span data-stu-id="f27c0-103">Assembly location</span></span>

<span data-ttu-id="f27c0-104">Lokalizacja zestawu określa, czy środowisko uruchomieniowe języka wspólnego może je zlokalizować w przypadku odwołania, a także określić, czy zestaw może być współużytkowany z innymi zestawami.</span><span class="sxs-lookup"><span data-stu-id="f27c0-104">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="f27c0-105">Zestaw można wdrożyć w następujących lokalizacjach:</span><span class="sxs-lookup"><span data-stu-id="f27c0-105">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="f27c0-106">Katalog lub podkatalogi aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f27c0-106">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="f27c0-107">Jest to najczęściej używane miejsce wdrożenia zestawu.</span><span class="sxs-lookup"><span data-stu-id="f27c0-107">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="f27c0-108">Podkatalogi katalogu głównego aplikacji mogą opierać się na języku lub kulturze.</span><span class="sxs-lookup"><span data-stu-id="f27c0-108">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="f27c0-109">Jeśli zestaw zawiera informacje w atrybucie Culture, musi znajdować się w podkatalogu w katalogu aplikacji z nazwą tej kultury.</span><span class="sxs-lookup"><span data-stu-id="f27c0-109">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="f27c0-110">Globalna pamięć podręczna zestawów.</span><span class="sxs-lookup"><span data-stu-id="f27c0-110">The global assembly cache.</span></span>

     <span data-ttu-id="f27c0-111">Jest to pamięć podręczna kodu całego komputera zainstalowana wszędzie tam, gdzie jest zainstalowany aparat plików wykonywalnych języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="f27c0-111">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="f27c0-112">W większości przypadków, jeśli zamierzasz udostępnić zestaw z wieloma aplikacjami, należy wdrożyć go w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="f27c0-112">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="f27c0-113">Na serwerze HTTP.</span><span class="sxs-lookup"><span data-stu-id="f27c0-113">On an HTTP server.</span></span>

     <span data-ttu-id="f27c0-114">Zestaw wdrożony na serwerze HTTP musi mieć silną nazwę; Wskaż zestaw w sekcji codebase w pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f27c0-114">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="f27c0-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f27c0-115">See also</span></span>

- [<span data-ttu-id="f27c0-116">Tworzenie zestawów</span><span class="sxs-lookup"><span data-stu-id="f27c0-116">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="f27c0-117">Globalna pamięć podręczna zestawów</span><span class="sxs-lookup"><span data-stu-id="f27c0-117">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="f27c0-118">Jak środowisko uruchomieniowe lokalizuje zestawy</span><span class="sxs-lookup"><span data-stu-id="f27c0-118">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
