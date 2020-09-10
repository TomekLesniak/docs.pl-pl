---
title: Zmiany powodujące niezgodność
description: Dowiedz się więcej o istotnych zmianach w każdej wersji platformy .NET Core.
ms.date: 11/27/2019
ms.openlocfilehash: eea6542acb9fa659af764bfd3a2af00fd9740191
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656278"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="cf13b-103">Selektory zmiany przerywania</span><span class="sxs-lookup"><span data-stu-id="cf13b-103">Breaking change selectors</span></span>

<span data-ttu-id="cf13b-104">Poniższe wersje i selektory obszarów zapewniają przefiltrowaną listę mających zastosowanie istotnych zmian między różnymi wersjami programu .NET Core, ASP.NET Core i EF Core.</span><span class="sxs-lookup"><span data-stu-id="cf13b-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="cf13b-105">Możesz również przejrzeć artykuły z wersjami lub technologiami obszarowymi w spisie treści.</span><span class="sxs-lookup"><span data-stu-id="cf13b-105">You can also browse version-to-version or technology area articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="cf13b-106">Według wersji</span><span class="sxs-lookup"><span data-stu-id="cf13b-106">By version</span></span>

<span data-ttu-id="cf13b-107">Wybierz aktualnie docelową wersję platformy .NET, a następnie wersję platformy .NET Core, do której chcesz przeprowadzić migrację:</span><span class="sxs-lookup"><span data-stu-id="cf13b-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

> [!div class="op_multi_selector" title1="Z wersji docelowej" title2="Do zmigrowanej wersji"]
>
> - [(3,1 | 5,0)](3.1-5.0.md)
> - [(3,0 | 3,1)](3.0-3.1.md)
> - [(2,2 | 3,1)](2.2-3.1.md)
> - [(2,2 | 3,0)](2.2-3.0.md)
> - [(2,0 | 2,1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a><span data-ttu-id="cf13b-116">Według obszaru technologii</span><span class="sxs-lookup"><span data-stu-id="cf13b-116">By technology area</span></span>

<span data-ttu-id="cf13b-117">Wybierz obszar technologii .NET Core, który Cię interesuje.</span><span class="sxs-lookup"><span data-stu-id="cf13b-117">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="cf13b-118">Indywidualne zmiany są uporządkowane według wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf13b-118">Individual changes are ordered by .NET Core version.</span></span>

> [!div class="op_single_selector"]
>
> - [ASP.NET Core](aspnetcore.md)
> - [Analiza kodu](code-analysis.md)
> - [Podstawowe biblioteki platformy .NET](corefx.md)
> - [Kryptografia](cryptography.md)
> - [EF Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
> - [Globalizacja](globalization.md)
> - [Interop](interop.md)
> - [Sieć](networking.md)
> - [Serializacja](serialization.md)
> - [Visual Basic](visualbasic.md)
> - [Windows Forms](winforms.md)
> - [WPF](wpf.md)

## <a name="github-issues-and-announcements"></a><span data-ttu-id="cf13b-131">Problemy i anonse w usłudze GitHub</span><span class="sxs-lookup"><span data-stu-id="cf13b-131">GitHub issues and announcements</span></span>

<span data-ttu-id="cf13b-132">Można również wyświetlić poszczególne problemy, które opisują istotne zmiany wprowadzone w programie .NET Core w następujących repozytoriach usługi GitHub:</span><span class="sxs-lookup"><span data-stu-id="cf13b-132">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="cf13b-133">W przypadku platformy .NET Core, repozytorium [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) .</span><span class="sxs-lookup"><span data-stu-id="cf13b-133">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="cf13b-134">Dla ASP.NET Core, repozytorium [ASPNET/anonsów](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) .</span><span class="sxs-lookup"><span data-stu-id="cf13b-134">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="cf13b-135">W przypadku Entity Framework Core, repozytorium [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) .</span><span class="sxs-lookup"><span data-stu-id="cf13b-135">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf13b-136">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cf13b-136">See also</span></span>

- [<span data-ttu-id="cf13b-137">Migrowanie z .NET Framework do platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="cf13b-137">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
