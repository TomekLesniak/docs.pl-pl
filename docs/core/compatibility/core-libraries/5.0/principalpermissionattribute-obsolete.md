---
title: 'Nieprzerwana zmiana: PrincipalPermissionAttribute jest przestarzała jako błąd'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których Konstruktor PrincipalPermissionAttribute jest przestarzały i powoduje błąd w czasie kompilacji.
ms.date: 11/01/2020
ms.openlocfilehash: 138bbf25fd493c1bb9c2b3f10b62681c735ea7b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761504"
---
# <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="25ba5-103">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="25ba5-103">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="25ba5-104"><xref:System.Security.Permissions.PrincipalPermissionAttribute>Konstruktor jest przestarzały i powoduje błąd w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="25ba5-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="25ba5-105">Nie można utworzyć wystąpienia tego atrybutu lub zastosować go do metody.</span><span class="sxs-lookup"><span data-stu-id="25ba5-105">You cannot instantiate this attribute or apply it to a method.</span></span>

## <a name="change-description"></a><span data-ttu-id="25ba5-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="25ba5-106">Change description</span></span>

<span data-ttu-id="25ba5-107">Na .NET Framework i .NET Core można dodawać adnotacje do metod przy użyciu <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="25ba5-107">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="25ba5-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="25ba5-108">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="25ba5-109">Począwszy od platformy .NET 5,0, nie można zastosować <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybutu do metody.</span><span class="sxs-lookup"><span data-stu-id="25ba5-109">Starting in .NET 5.0, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="25ba5-110">Konstruktor atrybutu jest przestarzały i tworzy błąd czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="25ba5-110">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="25ba5-111">W przeciwieństwie do innych ostrzeżeń obsoletion nie można pominąć tego błędu.</span><span class="sxs-lookup"><span data-stu-id="25ba5-111">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="25ba5-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="25ba5-112">Reason for change</span></span>

<span data-ttu-id="25ba5-113"><xref:System.Security.Permissions.PrincipalPermissionAttribute>Typ, podobnie jak inne typy, które podklasa <xref:System.Security.Permissions.SecurityAttribute> , jest częścią. Infrastruktura zabezpieczeń dostępu kodu (CAS) w sieci.</span><span class="sxs-lookup"><span data-stu-id="25ba5-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="25ba5-114">W .NET Framework 2. x-4. x środowisko uruchomieniowe wymusza <xref:System.Security.Permissions.PrincipalPermissionAttribute> adnotacje w wpisie metody, nawet jeśli aplikacja działa w ramach scenariusza pełnego zaufania.</span><span class="sxs-lookup"><span data-stu-id="25ba5-114">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="25ba5-115">Programy .NET Core i .NET 5,0 i nowsze nie obsługują atrybutów CAS, a środowisko uruchomieniowe je ignoruje.</span><span class="sxs-lookup"><span data-stu-id="25ba5-115">.NET Core and .NET 5.0 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="25ba5-116">Różnica w zachowaniu z .NET Framework do platformy .NET Core i programu .NET 5,0 może skutkować scenariuszem "Niepowodzenie otwarcia", gdzie dostęp powinien być zablokowany, ale zamiast tego jest dozwolony.</span><span class="sxs-lookup"><span data-stu-id="25ba5-116">This difference in behavior from .NET Framework to .NET Core and .NET 5.0 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="25ba5-117">Aby zapobiec scenariuszowi "Niepowodzenie otwarcia", nie można już zastosować atrybutu w kodzie, który jest przeznaczony dla programu .NET 5,0 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="25ba5-117">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5.0 or later.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="25ba5-118">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="25ba5-118">Version introduced</span></span>

<span data-ttu-id="25ba5-119">5,0</span><span class="sxs-lookup"><span data-stu-id="25ba5-119">5.0</span></span>

## <a name=""></a><span data-ttu-id="25ba5-120"><a id="permission-action">Zalecana akcja</a></span><span class="sxs-lookup"><span data-stu-id="25ba5-120"><a id="permission-action">Recommended action</a></span></span>

<span data-ttu-id="25ba5-121">W przypadku wystąpienia błędu obsoletion należy wykonać akcję.</span><span class="sxs-lookup"><span data-stu-id="25ba5-121">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="25ba5-122">**Jeśli stosujesz atrybut do metody akcji ASP.NET MVC:**</span><span class="sxs-lookup"><span data-stu-id="25ba5-122">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="25ba5-123">Rozważ użycie środowiska ASP. Wbudowana infrastruktura autoryzacji w sieci.</span><span class="sxs-lookup"><span data-stu-id="25ba5-123">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="25ba5-124">Poniższy kod ilustruje sposób dodawania adnotacji do kontrolera z <xref:System.Web.Mvc.AuthorizeAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="25ba5-124">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="25ba5-125">Środowisko uruchomieniowe ASP.NET będzie autoryzować użytkownika przed wykonaniem akcji.</span><span class="sxs-lookup"><span data-stu-id="25ba5-125">The ASP.NET runtime will authorize the user before performing the action.</span></span>

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  <span data-ttu-id="25ba5-126">Aby uzyskać więcej informacji, zobacz [Autoryzacja oparta na rolach w ASP.NET Core](/aspnet/core/security/authorization/roles) i [wprowadzenie do autoryzacji w programie ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="25ba5-126">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="25ba5-127">**Jeśli stosujesz atrybut do kodu biblioteki poza kontekstem aplikacji sieci Web:**</span><span class="sxs-lookup"><span data-stu-id="25ba5-127">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="25ba5-128">Ręcznie wykonaj testy na początku metody.</span><span class="sxs-lookup"><span data-stu-id="25ba5-128">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="25ba5-129">Można to zrobić za pomocą <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="25ba5-129">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

## <a name="affected-apis"></a><span data-ttu-id="25ba5-130">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="25ba5-130">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
