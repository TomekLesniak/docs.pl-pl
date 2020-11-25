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
# <a name="principalpermissionattribute-is-obsolete-as-error"></a>PrincipalPermissionAttribute jest przestarzały jako błąd

<xref:System.Security.Permissions.PrincipalPermissionAttribute>Konstruktor jest przestarzały i powoduje błąd w czasie kompilacji. Nie można utworzyć wystąpienia tego atrybutu lub zastosować go do metody.

## <a name="change-description"></a>Zmień opis

Na .NET Framework i .NET Core można dodawać adnotacje do metod przy użyciu <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybutu. Na przykład:

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

Począwszy od platformy .NET 5,0, nie można zastosować <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybutu do metody. Konstruktor atrybutu jest przestarzały i tworzy błąd czasu kompilacji. W przeciwieństwie do innych ostrzeżeń obsoletion nie można pominąć tego błędu.

## <a name="reason-for-change"></a>Przyczyna zmiany

<xref:System.Security.Permissions.PrincipalPermissionAttribute>Typ, podobnie jak inne typy, które podklasa <xref:System.Security.Permissions.SecurityAttribute> , jest częścią. Infrastruktura zabezpieczeń dostępu kodu (CAS) w sieci. W .NET Framework 2. x-4. x środowisko uruchomieniowe wymusza <xref:System.Security.Permissions.PrincipalPermissionAttribute> adnotacje w wpisie metody, nawet jeśli aplikacja działa w ramach scenariusza pełnego zaufania. Programy .NET Core i .NET 5,0 i nowsze nie obsługują atrybutów CAS, a środowisko uruchomieniowe je ignoruje.

Różnica w zachowaniu z .NET Framework do platformy .NET Core i programu .NET 5,0 może skutkować scenariuszem "Niepowodzenie otwarcia", gdzie dostęp powinien być zablokowany, ale zamiast tego jest dozwolony. Aby zapobiec scenariuszowi "Niepowodzenie otwarcia", nie można już zastosować atrybutu w kodzie, który jest przeznaczony dla programu .NET 5,0 lub nowszego.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name=""></a><a id="permission-action">Zalecana akcja</a>

W przypadku wystąpienia błędu obsoletion należy wykonać akcję.

- **Jeśli stosujesz atrybut do metody akcji ASP.NET MVC:**

  Rozważ użycie środowiska ASP. Wbudowana infrastruktura autoryzacji w sieci. Poniższy kod ilustruje sposób dodawania adnotacji do kontrolera z <xref:System.Web.Mvc.AuthorizeAttribute> atrybutem. Środowisko uruchomieniowe ASP.NET będzie autoryzować użytkownika przed wykonaniem akcji.

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

  Aby uzyskać więcej informacji, zobacz [Autoryzacja oparta na rolach w ASP.NET Core](/aspnet/core/security/authorization/roles) i [wprowadzenie do autoryzacji w programie ASP.NET Core](/aspnet/core/security/authorization/introduction).

- **Jeśli stosujesz atrybut do kodu biblioteki poza kontekstem aplikacji sieci Web:**

  Ręcznie wykonaj testy na początku metody. Można to zrobić za pomocą <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> metody.

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

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
