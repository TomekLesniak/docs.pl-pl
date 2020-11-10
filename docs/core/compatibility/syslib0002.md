---
title: Błąd SYSLIB0002
description: Dowiedz się więcej o obsoletion, który generuje błąd czasu kompilowania SYSLIB0002.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 53eb51d5e525c463e5698710bdb6fa0c0907e43c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440780"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a><span data-ttu-id="b49d3-103">SYSLIB0002: PrincipalPermissionAttribute jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="b49d3-103">SYSLIB0002: PrincipalPermissionAttribute is obsolete</span></span>

<span data-ttu-id="b49d3-104"><xref:System.Security.Permissions.PrincipalPermissionAttribute>Konstruktor jest przestarzały i generuje błąd czasu kompilacji `SYSLIB0002` , rozpoczynając od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="b49d3-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces compile-time error `SYSLIB0002`, starting in .NET 5.0.</span></span> <span data-ttu-id="b49d3-105">Nie można utworzyć wystąpienia tego atrybutu lub zastosować go do metody.</span><span class="sxs-lookup"><span data-stu-id="b49d3-105">You cannot instantiate this attribute or apply it to a method.</span></span>

<span data-ttu-id="b49d3-106">W przeciwieństwie do innych ostrzeżeń obsoletion nie można pominąć tego błędu.</span><span class="sxs-lookup"><span data-stu-id="b49d3-106">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="b49d3-107">Obejścia</span><span class="sxs-lookup"><span data-stu-id="b49d3-107">Workarounds</span></span>

- <span data-ttu-id="b49d3-108">Jeśli stosujesz atrybut do metody akcji ASP.NET MVC:</span><span class="sxs-lookup"><span data-stu-id="b49d3-108">If you're applying the attribute to an ASP.NET MVC action method:</span></span>

  <span data-ttu-id="b49d3-109">Rozważ użycie środowiska ASP. Wbudowana infrastruktura autoryzacji w sieci.</span><span class="sxs-lookup"><span data-stu-id="b49d3-109">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="b49d3-110">Poniższy kod ilustruje sposób dodawania adnotacji do kontrolera z <xref:System.Web.Mvc.AuthorizeAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="b49d3-110">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="b49d3-111">Środowisko uruchomieniowe ASP.NET będzie autoryzować użytkownika przed wykonaniem akcji.</span><span class="sxs-lookup"><span data-stu-id="b49d3-111">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="b49d3-112">Aby uzyskać więcej informacji, zobacz [Autoryzacja oparta na rolach w ASP.NET Core](/aspnet/core/security/authorization/roles) i [wprowadzenie do autoryzacji w programie ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="b49d3-112">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="b49d3-113">Jeśli stosujesz atrybut do kodu biblioteki poza kontekstem aplikacji sieci Web:</span><span class="sxs-lookup"><span data-stu-id="b49d3-113">If you're applying the attribute to library code outside the context of a web app:</span></span>

  <span data-ttu-id="b49d3-114">Ręcznie wykonaj testy na początku metody, wywołując <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="b49d3-114">Perform the checks manually at the beginning of your method by calling the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="b49d3-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b49d3-115">See also</span></span>

- [<span data-ttu-id="b49d3-116">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="b49d3-116">PrincipalPermissionAttribute is obsolete as error</span></span>](3.1-5.0.md#principalpermissionattribute-is-obsolete-as-error)
