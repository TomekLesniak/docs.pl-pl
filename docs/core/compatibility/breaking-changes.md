---
title: Fundamentalne zmiany
description: Dowiedz się więcej o istotnych zmianach w każdej wersji platformy .NET Core.
ms.date: 11/27/2019
ms.openlocfilehash: 550553ef14cd0635fbe4a5346c457a41264a4b82
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916264"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="c1e44-103">Selektory zmiany przerywania</span><span class="sxs-lookup"><span data-stu-id="c1e44-103">Breaking change selectors</span></span>

<span data-ttu-id="c1e44-104">Poniższe wersje i selektory obszarów zapewniają przefiltrowaną listę mających zastosowanie istotnych zmian między różnymi wersjami programu .NET Core, ASP.NET Core i EF Core.</span><span class="sxs-lookup"><span data-stu-id="c1e44-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="c1e44-105">Możesz również przejrzeć artykuły z wersjami lub technologiami obszarowymi w spisie treści.</span><span class="sxs-lookup"><span data-stu-id="c1e44-105">You can also browse version-to-version or technology area articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="c1e44-106">Według wersji</span><span class="sxs-lookup"><span data-stu-id="c1e44-106">By version</span></span>

<span data-ttu-id="c1e44-107">Wybierz aktualnie docelową wersję platformy .NET, a następnie wersję platformy .NET Core, do której chcesz przeprowadzić migrację:</span><span class="sxs-lookup"><span data-stu-id="c1e44-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

> [!div class="op_multi_selector" title1="Z wersji docelowej" title2="Do zmigrowanej wersji"]
>
> - [(3,1 | 5,0)](3.1-5.0.md)
> - [(3,0 | 3,1)](3.0-3.1.md)
> - [(2,2 | 3,1)](2.2-3.1.md)
> - [(2,2 | 3,0)](2.2-3.0.md)
> - [(2,0 | 2,1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a><span data-ttu-id="c1e44-116">Według obszaru technologii</span><span class="sxs-lookup"><span data-stu-id="c1e44-116">By technology area</span></span>

<span data-ttu-id="c1e44-117">Wybierz obszar technologii .NET Core, który Cię interesuje.</span><span class="sxs-lookup"><span data-stu-id="c1e44-117">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="c1e44-118">Indywidualne zmiany są uporządkowane według wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c1e44-118">Individual changes are ordered by .NET Core version.</span></span>

> [!div class="op_single_selector"]
>
> - [ASP.NET Core](aspnetcore.md)
> - [Podstawowe biblioteki platformy .NET](corefx.md)
> - [Kryptografia](cryptography.md)
> - [EF Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
> - [Globalizacja](globalization.md)
> - [Interop](interop.md)
> - [Sieć](networking.md)
> - [Serializacja](serialization.md)
> - [Visual Basic](visualbasic.md)
> - [Windows Forms](winforms.md)

## <a name="github-issues-and-announcements"></a><span data-ttu-id="c1e44-129">Problemy i anonse w usłudze GitHub</span><span class="sxs-lookup"><span data-stu-id="c1e44-129">GitHub issues and announcements</span></span>

<span data-ttu-id="c1e44-130">Można również wyświetlić poszczególne problemy, które opisują istotne zmiany wprowadzone w programie .NET Core w następujących repozytoriach usługi GitHub:</span><span class="sxs-lookup"><span data-stu-id="c1e44-130">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="c1e44-131">W przypadku platformy .NET Core, repozytorium [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) .</span><span class="sxs-lookup"><span data-stu-id="c1e44-131">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="c1e44-132">Dla ASP.NET Core, repozytorium [ASPNET/anonsów](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) .</span><span class="sxs-lookup"><span data-stu-id="c1e44-132">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="c1e44-133">W przypadku Entity Framework Core, repozytorium [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) .</span><span class="sxs-lookup"><span data-stu-id="c1e44-133">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1e44-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c1e44-134">See also</span></span>

- [<span data-ttu-id="c1e44-135">Migrowanie z .NET Framework do platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="c1e44-135">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
