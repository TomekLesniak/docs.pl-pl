---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032696"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="9ad08-101">Autoryzacja: implementacje IAuthorizationPolicyProvider wymagają nowej metody</span><span class="sxs-lookup"><span data-stu-id="9ad08-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="9ad08-102">W ASP.NET Core 3,0 `GetFallbackPolicyAsync` dodano nową metodę do `IAuthorizationPolicyProvider` .</span><span class="sxs-lookup"><span data-stu-id="9ad08-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="9ad08-103">Te zasady powrotu są używane przez oprogramowanie pośredniczące autoryzacji, gdy nie określono zasad.</span><span class="sxs-lookup"><span data-stu-id="9ad08-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="9ad08-104">Aby uzyskać więcej informacji, zobacz [dotnet/aspnetcore # 9759](https://github.com/dotnet/aspnetcore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="9ad08-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9ad08-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9ad08-105">Version introduced</span></span>

<span data-ttu-id="9ad08-106">3.0</span><span class="sxs-lookup"><span data-stu-id="9ad08-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9ad08-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="9ad08-107">Old behavior</span></span>

<span data-ttu-id="9ad08-108">Implementacje `IAuthorizationPolicyProvider` nie wymagały `GetFallbackPolicyAsync` metody.</span><span class="sxs-lookup"><span data-stu-id="9ad08-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9ad08-109">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="9ad08-109">New behavior</span></span>

<span data-ttu-id="9ad08-110">Implementacje `IAuthorizationPolicyProvider` wymagają `GetFallbackPolicyAsync` metody.</span><span class="sxs-lookup"><span data-stu-id="9ad08-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9ad08-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="9ad08-111">Reason for change</span></span>

<span data-ttu-id="9ad08-112">Nowa metoda była wymagana do `AuthorizationMiddleware` użycia w przypadku, gdy nie określono żadnych zasad.</span><span class="sxs-lookup"><span data-stu-id="9ad08-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9ad08-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9ad08-113">Recommended action</span></span>

<span data-ttu-id="9ad08-114">Dodaj `GetFallbackPolicyAsync` metodę do implementacji programu `IAuthorizationPolicyProvider` .</span><span class="sxs-lookup"><span data-stu-id="9ad08-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="9ad08-115">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9ad08-115">Category</span></span>

<span data-ttu-id="9ad08-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9ad08-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9ad08-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9ad08-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
