---
ms.openlocfilehash: 4dcb357570cb6597fde86c9e8f2acb74364cfaa3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032858"
---
### <a name="session-state-obsolete-apis-removed"></a><span data-ttu-id="beabf-101">Stan sesji: Usunięto przestarzałe interfejsy API</span><span class="sxs-lookup"><span data-stu-id="beabf-101">Session state: Obsolete APIs removed</span></span>

<span data-ttu-id="beabf-102">Usunięto przestarzałe interfejsy API służące do konfigurowania plików cookie sesji.</span><span class="sxs-lookup"><span data-stu-id="beabf-102">Obsolete APIs for configuring session cookies were removed.</span></span> <span data-ttu-id="beabf-103">Aby uzyskać więcej informacji, zobacz [ASPNET/anonse # 257](https://github.com/aspnet/Announcements/issues/257).</span><span class="sxs-lookup"><span data-stu-id="beabf-103">For more information, see [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="beabf-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="beabf-104">Version introduced</span></span>

<span data-ttu-id="beabf-105">3.0</span><span class="sxs-lookup"><span data-stu-id="beabf-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="beabf-106">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="beabf-106">Reason for change</span></span>

<span data-ttu-id="beabf-107">Ta zmiana wymusza spójność interfejsów API w celu konfigurowania funkcji używających plików cookie.</span><span class="sxs-lookup"><span data-stu-id="beabf-107">This change enforces consistency across APIs for configuring features that use cookies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="beabf-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="beabf-108">Recommended action</span></span>

<span data-ttu-id="beabf-109">Migruj użycie usuniętych interfejsów API do ich nowszych zamian.</span><span class="sxs-lookup"><span data-stu-id="beabf-109">Migrate usage of the removed APIs to their newer replacements.</span></span> <span data-ttu-id="beabf-110">Rozważmy następujący przykład w `Startup.ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="beabf-110">Consider the following example in `Startup.ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a><span data-ttu-id="beabf-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="beabf-111">Category</span></span>

<span data-ttu-id="beabf-112">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="beabf-112">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="beabf-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="beabf-113">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
