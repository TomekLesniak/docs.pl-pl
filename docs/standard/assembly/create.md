---
title: Tworzenie zestawów
description: Dowiedz się więcej na temat tworzenia zestawów jednoplikowych lub wieloplikowych przy użyciu środowiska IDE, takiego jak Visual Studio, lub kompilatorów i narzędzi dostarczanych przez Windows SDK.
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET], multifile
- single-file assemblies
- assemblies [.NET], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: e1b08e40ae3b4c377cec52cb1ebf6db643af6429
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160584"
---
# <a name="create-assemblies"></a><span data-ttu-id="2c8e1-103">Tworzenie zestawów</span><span class="sxs-lookup"><span data-stu-id="2c8e1-103">Create assemblies</span></span>

<span data-ttu-id="2c8e1-104">Można tworzyć zestawy Jednoplikowe lub wieloplikowe za pomocą IDE, takie jak Visual Studio, lub kompilatory i narzędzia dostarczone przez Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-104">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="2c8e1-105">Najprostszym zestawem jest pojedynczy plik, który ma prostą nazwę i jest ładowany do pojedynczej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-105">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="2c8e1-106">Ten zestaw nie może odwoływać się do innych zestawów poza katalogiem aplikacji i nie jest sprawdzany Sprawdzanie wersji.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-106">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="2c8e1-107">Aby odinstalować aplikację utworzoną z zestawu, wystarczy usunąć znajdujący się w niej katalog.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-107">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="2c8e1-108">W przypadku wielu deweloperów zestaw z tymi funkcjami jest wymagany do wdrożenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-108">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="2c8e1-109">Zestaw wieloplikowy można utworzyć z kilku modułów kodu i plików zasobów.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-109">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="2c8e1-110">Możesz również utworzyć zestaw, który może być współużytkowany przez wiele aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-110">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="2c8e1-111">Zestaw współużytkowany musi mieć silną nazwę i można go wdrożyć w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-111">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="2c8e1-112">Istnieje kilka opcji grupowania modułów kodu i zasobów w zestawy, w zależności od następujących czynników:</span><span class="sxs-lookup"><span data-stu-id="2c8e1-112">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="2c8e1-113">Przechowywanie wersji</span><span class="sxs-lookup"><span data-stu-id="2c8e1-113">Versioning</span></span>

     <span data-ttu-id="2c8e1-114">Grupuj moduły, które powinny mieć te same informacje o wersji.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-114">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="2c8e1-115">Wdrożenie</span><span class="sxs-lookup"><span data-stu-id="2c8e1-115">Deployment</span></span>

     <span data-ttu-id="2c8e1-116">Grupuj moduły kodu i zasoby, które obsługują model wdrażania.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-116">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="2c8e1-117">Ponowne użycie</span><span class="sxs-lookup"><span data-stu-id="2c8e1-117">Reuse</span></span>

     <span data-ttu-id="2c8e1-118">Grupuj moduły, jeśli mogą być logicznie używane razem do pewnego celu.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-118">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="2c8e1-119">Na przykład zestaw składający się z typów i klas używanych rzadko do konserwacji programu można umieścić w tym samym zestawie.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-119">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="2c8e1-120">Ponadto typy, które mają być współużytkowane z wieloma aplikacjami, powinny być pogrupowane w zestaw, a zestaw powinien być podpisany za pomocą silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-120">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="2c8e1-121">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="2c8e1-121">Security</span></span>

     <span data-ttu-id="2c8e1-122">Moduły grupy zawierające typy, które wymagają tych samych uprawnień zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-122">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="2c8e1-123">Zakresów</span><span class="sxs-lookup"><span data-stu-id="2c8e1-123">Scoping</span></span>

     <span data-ttu-id="2c8e1-124">Moduły grupy zawierające typy, których widoczność powinna być ograniczona do tego samego zestawu.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-124">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="2c8e1-125">Istnieją specjalne zagadnienia dotyczące tworzenia zestawów środowiska uruchomieniowego języka wspólnego dla niezarządzanych aplikacji COM.</span><span class="sxs-lookup"><span data-stu-id="2c8e1-125">There are special considerations when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="2c8e1-126">Aby uzyskać więcej informacji na temat pracy z kodem niezarządzanym, zobacz [udostępnianie .NET Framework składników do modelu COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="2c8e1-126">For more information about working with unmanaged code, see [Expose .NET Framework components to COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c8e1-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2c8e1-127">See also</span></span>

- [<span data-ttu-id="2c8e1-128">Przechowywanie wersji zestawu</span><span class="sxs-lookup"><span data-stu-id="2c8e1-128">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="2c8e1-129">Instrukcje: tworzenie zestawu jednoplikowego</span><span class="sxs-lookup"><span data-stu-id="2c8e1-129">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)
- [<span data-ttu-id="2c8e1-130">Instrukcje: tworzenie zestawów wieloplikowych</span><span class="sxs-lookup"><span data-stu-id="2c8e1-130">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="2c8e1-131">Jak środowisko uruchomieniowe lokalizuje zestawy</span><span class="sxs-lookup"><span data-stu-id="2c8e1-131">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="2c8e1-132">Zestawy wieloplikowe</span><span class="sxs-lookup"><span data-stu-id="2c8e1-132">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)
