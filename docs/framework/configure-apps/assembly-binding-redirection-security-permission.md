---
title: Uprawnienie zabezpieczeń przekierowania powiązania zestawu
description: Dowiedz się więcej o uprawnieniach zabezpieczeń wymaganych do jawnego przekierowania powiązania zestawu w pliku konfiguracyjnym aplikacji w programie .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: ea2b735b2c98b588903c4393f21c6b743910854a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552378"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="abcd6-103">Uprawnienie zabezpieczeń przekierowania powiązania zestawu</span><span class="sxs-lookup"><span data-stu-id="abcd6-103">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="abcd6-104">Jawne przekierowanie powiązań zestawu w pliku konfiguracji aplikacji wymaga uprawnienia zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="abcd6-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="abcd6-105">Dotyczy to przekierowań zestawów programu .NET Framework i zestawów firm trzecich.</span><span class="sxs-lookup"><span data-stu-id="abcd6-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="abcd6-106">Uprawnienie jest udzielane przez ustawienie <xref:System.Security.Permissions.SecurityPermissionFlag> flagi na <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="abcd6-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="abcd6-107">Zarządzane zestawy nie mają domyślnie żadnych uprawnień.</span><span class="sxs-lookup"><span data-stu-id="abcd6-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="abcd6-108">Uprawnienia zabezpieczeń są udzielane aplikacjom działającym w strefie zaufanej (komputer lokalny) i intranet.</span><span class="sxs-lookup"><span data-stu-id="abcd6-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="abcd6-109">Aplikacje działające w strefie Internetu są ściśle zabronione przed przekierowaniem powiązań zestawu.</span><span class="sxs-lookup"><span data-stu-id="abcd6-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="abcd6-110">Uprawnienie nie jest wymagane, jeśli przekierowanie zestawu jest wykonywane w pliku zasad wydawcy, który jest kontrolowany przez wydawcę składnika lub w pliku konfiguracyjnym komputera kontrolowanym przez administratora.</span><span class="sxs-lookup"><span data-stu-id="abcd6-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="abcd6-111">Jednak uprawnienie jest wymagane, aby aplikacja jawnie ignorował zasady wydawcy przy użyciu [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) elementu w pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="abcd6-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="abcd6-112">W poniższej tabeli przedstawiono domyślne ustawienia zabezpieczeń flagi **BindingRedirects** .</span><span class="sxs-lookup"><span data-stu-id="abcd6-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="abcd6-113">Strefa</span><span class="sxs-lookup"><span data-stu-id="abcd6-113">Zone</span></span>|<span data-ttu-id="abcd6-114">Ustawienie flagi BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="abcd6-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="abcd6-115">Strefa zaufana (maszyna lokalna)</span><span class="sxs-lookup"><span data-stu-id="abcd6-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="abcd6-116">**Z**</span><span class="sxs-lookup"><span data-stu-id="abcd6-116">**ON**</span></span>|  
|<span data-ttu-id="abcd6-117">Strefa intranetowa</span><span class="sxs-lookup"><span data-stu-id="abcd6-117">Intranet Zone</span></span>|<span data-ttu-id="abcd6-118">**Z**</span><span class="sxs-lookup"><span data-stu-id="abcd6-118">**ON**</span></span>|  
|<span data-ttu-id="abcd6-119">Strefa Internet</span><span class="sxs-lookup"><span data-stu-id="abcd6-119">Internet Zone</span></span>|<span data-ttu-id="abcd6-120">**Logowanie**</span><span class="sxs-lookup"><span data-stu-id="abcd6-120">**OFF**</span></span>|  
|<span data-ttu-id="abcd6-121">Niezaufane strefy</span><span class="sxs-lookup"><span data-stu-id="abcd6-121">Untrusted zones</span></span>|<span data-ttu-id="abcd6-122">**Logowanie**</span><span class="sxs-lookup"><span data-stu-id="abcd6-122">**OFF**</span></span>|  
  
 <span data-ttu-id="abcd6-123">Administrator może zmienić te ustawienia zabezpieczeń, aby obsługiwać lub ograniczać określone scenariusze na danym komputerze.</span><span class="sxs-lookup"><span data-stu-id="abcd6-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="abcd6-124">Nie ma narzędzi do zmiany ustawienia flagi **BindingRedirects** z domyślnego. Administrator musi ręcznie edytować plik Security.config na komputerze użytkownika.</span><span class="sxs-lookup"><span data-stu-id="abcd6-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcd6-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="abcd6-125">See also</span></span>

- <span data-ttu-id="abcd6-126">[Pliki zasad wydawcy i wykonywanie równoczesne](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="abcd6-126">[Publisher Policy Files and Side-by-Side Execution](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="abcd6-127">Instrukcje: Włączanie i wyłączanie automatycznego przekierowania powiązań</span><span class="sxs-lookup"><span data-stu-id="abcd6-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="abcd6-128">Wykonywanie równoczesne</span><span class="sxs-lookup"><span data-stu-id="abcd6-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
