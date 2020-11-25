---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032808"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="aff2e-101">Kestrel: Usunięto pusty zestaw HTTPS</span><span class="sxs-lookup"><span data-stu-id="aff2e-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="aff2e-102">Zestaw został <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> usunięty.</span><span class="sxs-lookup"><span data-stu-id="aff2e-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aff2e-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="aff2e-103">Version introduced</span></span>

<span data-ttu-id="aff2e-104">3.0</span><span class="sxs-lookup"><span data-stu-id="aff2e-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aff2e-105">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="aff2e-105">Reason for change</span></span>

<span data-ttu-id="aff2e-106">W ASP.NET Core 2,1 zawartość `Microsoft.AspNetCore.Server.Kestrel.Https` została przeniesiona do lokalizacji <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="aff2e-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="aff2e-107">Ta zmiana została wykonana w sposób rozdzielny przy użyciu `[TypeForwardedTo]` atrybutów.</span><span class="sxs-lookup"><span data-stu-id="aff2e-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aff2e-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="aff2e-108">Recommended action</span></span>

- <span data-ttu-id="aff2e-109">Biblioteki, do których odwołuje `Microsoft.AspNetCore.Server.Kestrel.Https` się 2,0, powinny aktualizować wszystkie zależności ASP.NET Core do 2,1 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="aff2e-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="aff2e-110">W przeciwnym razie mogą wystąpić przerwy w przypadku załadowania do aplikacji ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="aff2e-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="aff2e-111">Aplikacje i biblioteki ukierunkowane na ASP.NET Core 2,1 i nowsze powinny usunąć wszystkie bezpośrednie odwołania do `Microsoft.AspNetCore.Server.Kestrel.Https` pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="aff2e-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="aff2e-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="aff2e-112">Category</span></span>

<span data-ttu-id="aff2e-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aff2e-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aff2e-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="aff2e-114">Affected APIs</span></span>

<span data-ttu-id="aff2e-115">Brak</span><span class="sxs-lookup"><span data-stu-id="aff2e-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
