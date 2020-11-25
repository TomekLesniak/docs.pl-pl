---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032791"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="f550d-101">Tożsamość: Konstruktor SignInManager akceptuje nowy parametr</span><span class="sxs-lookup"><span data-stu-id="f550d-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="f550d-102">Począwszy od ASP.NET Core 3,0, `IUserConfirmation<TUser>` do konstruktora został dodany nowy parametr `SignInManager` .</span><span class="sxs-lookup"><span data-stu-id="f550d-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="f550d-103">Aby uzyskać więcej informacji, zobacz [dotnet/aspnetcore # 8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="f550d-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f550d-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f550d-104">Version introduced</span></span>

<span data-ttu-id="f550d-105">3.0</span><span class="sxs-lookup"><span data-stu-id="f550d-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f550d-106">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="f550d-106">Reason for change</span></span>

<span data-ttu-id="f550d-107">Celem zmiany było dodanie obsługi nowych przepływów poczty e-mail/potwierdzenia w tożsamości.</span><span class="sxs-lookup"><span data-stu-id="f550d-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f550d-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="f550d-108">Recommended action</span></span>

<span data-ttu-id="f550d-109">W przypadku ręcznego konstruowania `SignInManager` , należy podać implementację `IUserConfirmation` lub pobrać jeden z iniekcji zależności, aby zapewnić.</span><span class="sxs-lookup"><span data-stu-id="f550d-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="f550d-110">Kategoria</span><span class="sxs-lookup"><span data-stu-id="f550d-110">Category</span></span>

<span data-ttu-id="f550d-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f550d-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f550d-112">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f550d-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
