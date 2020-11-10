---
title: 'NETSDK1071: element PackageReference dla elementu " {0} " określił wersję programu `{1}` .'
description: Jak rozwiązać problem PackageReference z pakietem w środowisku z wersją programu.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445782"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a><span data-ttu-id="9f442-103">NETSDK1071: jawnie wersja PackageReference do pakietu, który będzie dołączany do platformy.</span><span class="sxs-lookup"><span data-stu-id="9f442-103">NETSDK1071: Explicitly versioned PackageReference to a metapackage that would be included with the framework.</span></span>

<span data-ttu-id="9f442-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="9f442-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="9f442-105">Gdy zestaw SDK programu .NET wystawia ostrzeżenie NETSDK1071, sugeruje on, że w przyszłości występuje konflikt wersji między wersją pakietu, który jest określony w PackageReference i wersja tego pakietu, jako niejawnie przywoływana za pośrednictwem właściwości TargetFramework:</span><span class="sxs-lookup"><span data-stu-id="9f442-105">When the .NET SDK issues warning NETSDK1071, it suggests there may be a version conflict in the future between the version of a metapackage specified in a PackageReference and the version of that metapackage as implicitly referenced via a TargetFramework property:</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="9f442-106">Ponieważ TargetFramework automatycznie jest w wersji pakietu, jego wersje będą powodować konflikty.</span><span class="sxs-lookup"><span data-stu-id="9f442-106">Since the TargetFramework automatically brings in a version of the metapackage, the versions will conflict should they ever differ.</span></span>

<span data-ttu-id="9f442-107">Aby rozwiązać ten problem:</span><span class="sxs-lookup"><span data-stu-id="9f442-107">To resolve this:</span></span>

1. <span data-ttu-id="9f442-108">Należy wziąć pod uwagę, że podczas określania wartości docelowej .NET Core lub .NET Standard, unikając jawnych odwołań do `Microsoft.NETCore.App` lub `NETStandard.Library` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="9f442-108">Consider, when targeting .NET Core or .NET Standard, avoiding explicit references to `Microsoft.NETCore.App` or `NETStandard.Library` in your project file.</span></span>
2. <span data-ttu-id="9f442-109">Jeśli potrzebujesz określonej wersji środowiska uruchomieniowego w przypadku określania wartości docelowej .NET Core, użyj `<RuntimeFrameworkVersion>` Właściwości zamiast bezpośrednio odwoływać się do pakietu.</span><span class="sxs-lookup"><span data-stu-id="9f442-109">If you need a specific version of the runtime when targeting .NET Core, use the `<RuntimeFrameworkVersion>`property instead of referencing the metapackage directly.</span></span> <span data-ttu-id="9f442-110">Na przykład może się tak zdarzyć, jeśli używasz [preinstalowanych wdrożeń](../../deploying/index.md#publish-self-contained) i potrzebujesz określonej poprawki środowiska uruchomieniowego 1.0.0 LTS.</span><span class="sxs-lookup"><span data-stu-id="9f442-110">As an example, this could happen if you're using [self-contained deployments](../../deploying/index.md#publish-self-contained) and need a specific patch of the 1.0.0 LTS runtime.</span></span>
3. <span data-ttu-id="9f442-111">Jeśli potrzebujesz określonej wersji programu `NetStandard.Library` podczas określania wartości docelowej .NET Standard, możesz użyć `<NetStandardImplicitPackageVersion>` właściwości i ustawić ją na wymaganą wersję.</span><span class="sxs-lookup"><span data-stu-id="9f442-111">If you need a specific version of `NetStandard.Library` when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set it to the version you need.</span></span>
4. <span data-ttu-id="9f442-112">Nie eplicitlyj dodawać ani aktualizować odwołań do `Microsoft.NETCore.App` ani `NETSTandard.Library` w projektach .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f442-112">Don't eplicitly add or update references to either `Microsoft.NETCore.App` or `NETSTandard.Library` in .NET Framework projects.</span></span> <span data-ttu-id="9f442-113">Pakiet NuGet automatycznie instaluje dowolną wersję `NETStandard.Library` potrzebną w przypadku korzystania z pakietu NuGet opartego na .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9f442-113">NuGet automatically installs any version of `NETStandard.Library` you need when using a .NET Standard-based NuGet package.</span></span>
5. <span data-ttu-id="9f442-114">Nie określaj wersji programu `Microsoft.AspNetCore.App` ani w `Microsoft.AspNetCore.All` przypadku korzystania z programu .NET Core 2.1 +, ponieważ zestaw .NET Core SDK automatycznie wybiera odpowiednią wersję.</span><span class="sxs-lookup"><span data-stu-id="9f442-114">Do not specify a version for `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` when using .NET Core 2.1+, as the .NET Core SDK automatically selects the appropriate version.</span></span> <span data-ttu-id="9f442-115">(Uwaga: Ta funkcja działa tylko wtedy, gdy program .NET Core 2,1 jest również wykorzystywany przez projekt) `Microsoft.NET.Sdk.Web` .</span><span class="sxs-lookup"><span data-stu-id="9f442-115">(Note: This only works when targeting .NET Core 2.1 if the project also uses `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="9f442-116">Ten problem został rozwiązany w zestawie SDK platformy .NET Core 2,2).</span><span class="sxs-lookup"><span data-stu-id="9f442-116">This problem was resolved in the .NET Core 2.2 SDK.)</span></span>
6. <span data-ttu-id="9f442-117">Jeśli chcesz, aby ostrzeżenie zostało odrzucone, możesz je również wyłączyć:</span><span class="sxs-lookup"><span data-stu-id="9f442-117">If you want the warning to go away, you can also disable it:</span></span>

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
