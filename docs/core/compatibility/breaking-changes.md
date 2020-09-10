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
# <a name="breaking-change-selectors"></a>Selektory zmiany przerywania

Poniższe wersje i selektory obszarów zapewniają przefiltrowaną listę mających zastosowanie istotnych zmian między różnymi wersjami programu .NET Core, ASP.NET Core i EF Core. Możesz również przejrzeć artykuły z wersjami lub technologiami obszarowymi w spisie treści.

## <a name="by-version"></a>Według wersji

Wybierz aktualnie docelową wersję platformy .NET, a następnie wersję platformy .NET Core, do której chcesz przeprowadzić migrację:

> [!div class="op_multi_selector" title1="Z wersji docelowej" title2="Do zmigrowanej wersji"]
>
> - [(3,1 | 5,0)](3.1-5.0.md)
> - [(3,0 | 3,1)](3.0-3.1.md)
> - [(2,2 | 3,1)](2.2-3.1.md)
> - [(2,2 | 3,0)](2.2-3.0.md)
> - [(2,0 | 2,1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a>Według obszaru technologii

Wybierz obszar technologii .NET Core, który Cię interesuje. Indywidualne zmiany są uporządkowane według wersji platformy .NET Core.

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

## <a name="github-issues-and-announcements"></a>Problemy i anonse w usłudze GitHub

Można również wyświetlić poszczególne problemy, które opisują istotne zmiany wprowadzone w programie .NET Core w następujących repozytoriach usługi GitHub:

- W przypadku platformy .NET Core, repozytorium [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) .
- Dla ASP.NET Core, repozytorium [ASPNET/anonsów](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) .
- W przypadku Entity Framework Core, repozytorium [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) .

## <a name="see-also"></a>Zobacz także

- [Migrowanie z .NET Framework do platformy .NET Core](../porting/index.md)
