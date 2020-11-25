---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032784"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="a5031-101">Tożsamość: Usunięto Przeciążenie metody AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="a5031-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="a5031-102">Począwszy od ASP.NET Core 3,0, Przeciążenie metody [IdentityBuilderUIExtensions. AddDefaultUI (IdentityBuilder, UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) już nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="a5031-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a5031-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a5031-103">Version introduced</span></span>

<span data-ttu-id="a5031-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a5031-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a5031-105">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a5031-105">Reason for change</span></span>

<span data-ttu-id="a5031-106">Ta zmiana była wynikiem przyjęcia funkcji statyczne elementy zawartości sieci Web.</span><span class="sxs-lookup"><span data-stu-id="a5031-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a5031-107">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a5031-107">Recommended action</span></span>

<span data-ttu-id="a5031-108">Wywołanie <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> zamiast przeciążenia, które przyjmuje dwa argumenty.</span><span class="sxs-lookup"><span data-stu-id="a5031-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="a5031-109">Jeśli używasz narzędzia Bootstrap 3, Dodaj również następujący wiersz do `<PropertyGroup>` elementu w pliku projektu:</span><span class="sxs-lookup"><span data-stu-id="a5031-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="a5031-110">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a5031-110">Category</span></span>

<span data-ttu-id="a5031-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a5031-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5031-112">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a5031-112">Affected APIs</span></span>

[<span data-ttu-id="a5031-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="a5031-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
