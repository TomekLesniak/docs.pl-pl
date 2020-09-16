---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539509"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="ebda8-101">Uwierzytelnianie: AzureAD. UI i AzureADB2C. interfejs API i pakiety oznaczone jako przestarzałe</span><span class="sxs-lookup"><span data-stu-id="ebda8-101">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="ebda8-102">W ASP.NET Core 2,1 Integracja z uwierzytelnianiem za pomocą usługi Azure Active Directory (Azure AD) i Azure Active Directory B2C (Azure AD B2C) jest zapewniana przez pakiety [Microsoft. AspNetCore. Authentication. AzureAD. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) i [Microsoft. AspNetCore. Authentication. AzureADB2C. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) .</span><span class="sxs-lookup"><span data-stu-id="ebda8-102">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="ebda8-103">Funkcje udostępniane przez te pakiety są oparte na punkcie końcowym usługi Azure AD v 1.0.</span><span class="sxs-lookup"><span data-stu-id="ebda8-103">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="ebda8-104">W ASP.NET Core 5,0 i nowszych integrację z usługą Azure AD i uwierzytelnianiem Azure AD B2C są udostępniane przez pakiet [Microsoft. Identity. Web](https://www.nuget.org/packages/Microsoft.Identity.Web) .</span><span class="sxs-lookup"><span data-stu-id="ebda8-104">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="ebda8-105">Ten pakiet jest oparty na platformie tożsamości firmy Microsoft, która jest znana wcześniej jako punkt końcowy usługi Azure AD v 2.0.</span><span class="sxs-lookup"><span data-stu-id="ebda8-105">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="ebda8-106">W związku z tym stare interfejsy API w `Microsoft.AspNetCore.Authentication.AzureAD.UI` `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` pakietach i były przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="ebda8-106">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="ebda8-107">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25807](https://github.com/dotnet/aspnetcore/issues/25807).</span><span class="sxs-lookup"><span data-stu-id="ebda8-107">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ebda8-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ebda8-108">Version introduced</span></span>

<span data-ttu-id="ebda8-109">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="ebda8-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ebda8-110">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="ebda8-110">Old behavior</span></span>

<span data-ttu-id="ebda8-111">Interfejsy API nie zostały oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="ebda8-111">The APIs weren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ebda8-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="ebda8-112">New behavior</span></span>

<span data-ttu-id="ebda8-113">Interfejsy API są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="ebda8-113">The APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ebda8-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ebda8-114">Reason for change</span></span>

<span data-ttu-id="ebda8-115">Funkcje uwierzytelniania usługi Azure AD i Azure AD B2C zostały zmigrowane do interfejsów API Microsoft Authentication Library (MSAL), które są dostępne w programie `Microsoft.Identity.Web` .</span><span class="sxs-lookup"><span data-stu-id="ebda8-115">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ebda8-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ebda8-116">Recommended action</span></span>

<span data-ttu-id="ebda8-117">Postępuj zgodnie ze `Microsoft.Identity.Web` wskazówkami interfejsu API dotyczącymi [aplikacji sieci Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) i [interfejsów API sieci Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span><span class="sxs-lookup"><span data-stu-id="ebda8-117">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

#### <a name="category"></a><span data-ttu-id="ebda8-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="ebda8-118">Category</span></span>

<span data-ttu-id="ebda8-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ebda8-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ebda8-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ebda8-120">Affected APIs</span></span>

* [<span data-ttu-id="ebda8-121">Microsoft. AspNetCore. Authentication. AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="ebda8-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="ebda8-122">Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="ebda8-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="ebda8-123">Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="ebda8-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="ebda8-124">Microsoft. AspNetCore. Authentication. AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="ebda8-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="ebda8-125">Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="ebda8-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="ebda8-126">Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="ebda8-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
