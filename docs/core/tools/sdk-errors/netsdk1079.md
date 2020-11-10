---
title: 'NETSDK1079: pakiet Microsoft. AspNetCore. All nie jest obsługiwany w przypadku programu .NET Core 3,0 lub nowszego.'
description: Jak rozwiązać migrację do programu Microsoft. AspNetCore. App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445781"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a><span data-ttu-id="85e92-103">NETSDK1079: pakiet Microsoft. AspNetCore. All nie jest obsługiwany w przypadku programu .NET Core 3,0 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="85e92-103">NETSDK1079: The Microsoft.AspNetCore.All package is not supported when targeting .NET Core 3.0 or higher.</span></span>

<span data-ttu-id="85e92-104">**Ten artykuł ma zastosowanie do:** ✔️ zestaw .NET Core SDK 3.1.100 i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="85e92-104">**This article applies to:** ✔️ .NET Core SDK 3.1.100 and later versions</span></span>

<span data-ttu-id="85e92-105">Ten komunikat o błędzie może pojawić się w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="85e92-105">You may receive this error message when:</span></span>

- <span data-ttu-id="85e92-106">Należy przekierować projekt ASP.NET Core z platformy .NET Core 2,2 lub starszej do programu .NET Core 3,0 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="85e92-106">You retarget an ASP.NET Core project from .NET Core 2.2 or earlier to .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="85e92-107">Projekt używa pakietu Microsoft. AspNetCore. ALL.</span><span class="sxs-lookup"><span data-stu-id="85e92-107">The project uses the Microsoft.AspNetCore.All package.</span></span>

<span data-ttu-id="85e92-108">Usuń `PackageReference` dla elementu Microsoft. AspNetCore. ALL.</span><span class="sxs-lookup"><span data-stu-id="85e92-108">Remove the `PackageReference` for Microsoft.AspNetCore.All.</span></span>  <span data-ttu-id="85e92-109">Może być również konieczne dodanie odwołań pakietu dla pakietów, do których odwołuje się element Microsoft. AspNetCore. All, ale nie są uwzględnione w infrastrukturze udostępnionej ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="85e92-109">You may also need to add package references for packages that were referenced from Microsoft.AspNetCore.All but are not included in the ASP.NET Core shared framework.</span></span>  <span data-ttu-id="85e92-110">Te pakiety są wymienione tutaj: [Migrowanie z Microsoft. AspNetCore. All do Microsoft. AspNetCore. app](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="85e92-110">These packages are listed here: [Migrating from Microsoft.AspNetCore.All to Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span></span>

<span data-ttu-id="85e92-111">Zobacz również [Migrowanie z ASP.NET Core 2,2 do 3,0](/aspnet/core/migration/22-to-30)</span><span class="sxs-lookup"><span data-stu-id="85e92-111">See also [Migrate from ASP.NET Core 2.2 to 3.0](/aspnet/core/migration/22-to-30)</span></span>
