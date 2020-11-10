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
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a>NETSDK1071: jawnie wersja PackageReference do pakietu, który będzie dołączany do platformy.

**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100 SDK i nowszych wersji

Gdy zestaw SDK programu .NET wystawia ostrzeżenie NETSDK1071, sugeruje on, że w przyszłości występuje konflikt wersji między wersją pakietu, który jest określony w PackageReference i wersja tego pakietu, jako niejawnie przywoływana za pośrednictwem właściwości TargetFramework:

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Ponieważ TargetFramework automatycznie jest w wersji pakietu, jego wersje będą powodować konflikty.

Aby rozwiązać ten problem:

1. Należy wziąć pod uwagę, że podczas określania wartości docelowej .NET Core lub .NET Standard, unikając jawnych odwołań do `Microsoft.NETCore.App` lub `NETStandard.Library` w pliku projektu.
2. Jeśli potrzebujesz określonej wersji środowiska uruchomieniowego w przypadku określania wartości docelowej .NET Core, użyj `<RuntimeFrameworkVersion>` Właściwości zamiast bezpośrednio odwoływać się do pakietu. Na przykład może się tak zdarzyć, jeśli używasz [preinstalowanych wdrożeń](../../deploying/index.md#publish-self-contained) i potrzebujesz określonej poprawki środowiska uruchomieniowego 1.0.0 LTS.
3. Jeśli potrzebujesz określonej wersji programu `NetStandard.Library` podczas określania wartości docelowej .NET Standard, możesz użyć `<NetStandardImplicitPackageVersion>` właściwości i ustawić ją na wymaganą wersję.
4. Nie eplicitlyj dodawać ani aktualizować odwołań do `Microsoft.NETCore.App` ani `NETSTandard.Library` w projektach .NET Framework. Pakiet NuGet automatycznie instaluje dowolną wersję `NETStandard.Library` potrzebną w przypadku korzystania z pakietu NuGet opartego na .NET Standard.
5. Nie określaj wersji programu `Microsoft.AspNetCore.App` ani w `Microsoft.AspNetCore.All` przypadku korzystania z programu .NET Core 2.1 +, ponieważ zestaw .NET Core SDK automatycznie wybiera odpowiednią wersję. (Uwaga: Ta funkcja działa tylko wtedy, gdy program .NET Core 2,1 jest również wykorzystywany przez projekt) `Microsoft.NET.Sdk.Web` . Ten problem został rozwiązany w zestawie SDK platformy .NET Core 2,2).
6. Jeśli chcesz, aby ostrzeżenie zostało odrzucone, możesz je również wyłączyć:

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
