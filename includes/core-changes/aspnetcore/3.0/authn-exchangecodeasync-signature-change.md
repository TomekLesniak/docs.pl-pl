---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394282"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="2eb86-101">Uwierzytelnianie: OAuthHandler ExchangeCodeAsync zmieniono sygnaturę</span><span class="sxs-lookup"><span data-stu-id="2eb86-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="2eb86-102">W ASP.NET Core 3,0 sygnatura `OAuthHandler.ExchangeCodeAsync` została zmieniona z:</span><span class="sxs-lookup"><span data-stu-id="2eb86-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="2eb86-103">Do:</span><span class="sxs-lookup"><span data-stu-id="2eb86-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="2eb86-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2eb86-104">Version introduced</span></span>

<span data-ttu-id="2eb86-105">3,0</span><span class="sxs-lookup"><span data-stu-id="2eb86-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2eb86-106">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="2eb86-106">Old behavior</span></span>

<span data-ttu-id="2eb86-107">`code`Ciągi i `redirectUri` zostały przekazane jako oddzielne argumenty.</span><span class="sxs-lookup"><span data-stu-id="2eb86-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2eb86-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="2eb86-108">New behavior</span></span>

<span data-ttu-id="2eb86-109">`Code` i `RedirectUri` są właściwościami `OAuthCodeExchangeContext` , które można ustawić za pośrednictwem `OAuthCodeExchangeContext` konstruktora.</span><span class="sxs-lookup"><span data-stu-id="2eb86-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="2eb86-110">Nowy `OAuthCodeExchangeContext` Typ jest jedynym argumentem przesłanym do `OAuthHandler.ExchangeCodeAsync` .</span><span class="sxs-lookup"><span data-stu-id="2eb86-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2eb86-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="2eb86-111">Reason for change</span></span>

<span data-ttu-id="2eb86-112">Ta zmiana pozwala na dostarczenie dodatkowych parametrów w sposób rozdzielny.</span><span class="sxs-lookup"><span data-stu-id="2eb86-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="2eb86-113">Nie ma potrzeby tworzenia nowych `ExchangeCodeAsync` przeciążeń.</span><span class="sxs-lookup"><span data-stu-id="2eb86-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2eb86-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="2eb86-114">Recommended action</span></span>

<span data-ttu-id="2eb86-115">Utwórz `OAuthCodeExchangeContext` z odpowiednimi `code` `redirectUri` wartościami i.</span><span class="sxs-lookup"><span data-stu-id="2eb86-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="2eb86-116"><xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>Należy podać wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="2eb86-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="2eb86-117">To pojedyncze `OAuthCodeExchangeContext` wystąpienie można przesłać `OAuthHandler.ExchangeCodeAsync` zamiast wielu argumentów.</span><span class="sxs-lookup"><span data-stu-id="2eb86-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="2eb86-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="2eb86-118">Category</span></span>

<span data-ttu-id="2eb86-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2eb86-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2eb86-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2eb86-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
