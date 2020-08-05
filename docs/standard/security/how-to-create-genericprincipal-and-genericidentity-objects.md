---
title: 'Instrukcje: Tworzenie obiektów GenericPrincipal i GenericIdentity'
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
ms.openlocfilehash: 903d636938c47850951330d7936d95470441607e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557219"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="f4344-102">Instrukcje: Tworzenie obiektów GenericPrincipal i GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="f4344-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

> [!NOTE]
> <span data-ttu-id="f4344-103">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f4344-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="f4344-104">Aby uzyskać informacje na temat ASP.NET Core, zobacz [Omówienie zabezpieczeń ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="f4344-104">For information about ASP.NET Core, see [Overview of ASP.NET Core Security](https://docs.microsoft.com/aspnet/core/security/).</span></span>

<span data-ttu-id="f4344-105">Można użyć <xref:System.Security.Principal.GenericIdentity> klasy w połączeniu z <xref:System.Security.Principal.GenericPrincipal> klasą, aby utworzyć schemat autoryzacji, który istnieje niezależnie od domeny systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f4344-105">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="f4344-106">Aby utworzyć obiekt GenericPrincipal —</span><span class="sxs-lookup"><span data-stu-id="f4344-106">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="f4344-107">Utwórz nowe wystąpienie klasy Identity i zainicjuj je nazwą, która ma zostać wstrzymana.</span><span class="sxs-lookup"><span data-stu-id="f4344-107">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="f4344-108">Poniższy kod tworzy nowy obiekt **GenericIdentity** i inicjuje go nazwą `MyUser` .</span><span class="sxs-lookup"><span data-stu-id="f4344-108">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="f4344-109">Utwórz nowe wystąpienie klasy **GenericPrincipal —** i zainicjuj je za pomocą wcześniej utworzonego obiektu **GenericIdentity** i tablicy ciągów reprezentujących role, które mają być skojarzone z tym podmiotem zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="f4344-109">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="f4344-110">Poniższy przykład kodu określa tablicę ciągów, które reprezentują rolę administratora i rolę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f4344-110">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="f4344-111">**GenericPrincipal —** zostaje następnie zainicjowany z poprzednią **GenericIdentity** i tablicą ciągów.</span><span class="sxs-lookup"><span data-stu-id="f4344-111">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="f4344-112">Użyj poniższego kodu, aby dołączyć podmiot zabezpieczeń do bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="f4344-112">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="f4344-113">Jest to przydatne w sytuacjach, w których podmiot zabezpieczeń musi być zweryfikowany kilka razy, musi być zweryfikowany przez inny kod uruchomiony w aplikacji lub musi być zweryfikowany przez <xref:System.Security.Permissions.PrincipalPermission> obiekt.</span><span class="sxs-lookup"><span data-stu-id="f4344-113">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="f4344-114">Można nadal wykonywać walidację na obiekcie Principal, bez dołączania go do wątku.</span><span class="sxs-lookup"><span data-stu-id="f4344-114">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="f4344-115">Aby uzyskać więcej informacji, zobacz [zastępowanie obiektu podmiotu zabezpieczeń](replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="f4344-115">For more information, see [Replacing a Principal Object](replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="f4344-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="f4344-116">Example</span></span>

<span data-ttu-id="f4344-117">Poniższy przykład kodu demonstruje, jak utworzyć wystąpienie elementu **GenericPrincipal —** i **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="f4344-117">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="f4344-118">Ten kod wyświetla wartości tych obiektów w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="f4344-118">This code displays the values of these objects to the console.</span></span>

```vb
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

    End Sub

End Class
```

```csharp
using System;
using System.Security.Principal;
using System.Threading;

public class Class1
{
    public static int Main(string[] args)
    {
    // Create generic identity.
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

<span data-ttu-id="f4344-119">Po wykonaniu aplikacja wyświetli dane wyjściowe podobne do poniższych.</span><span class="sxs-lookup"><span data-stu-id="f4344-119">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="f4344-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f4344-120">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="f4344-121">Zastępowanie obiektu głównego</span><span class="sxs-lookup"><span data-stu-id="f4344-121">Replacing a Principal Object</span></span>](replacing-a-principal-object.md)
- [<span data-ttu-id="f4344-122">Obiekty główne i obiekty tożsamości</span><span class="sxs-lookup"><span data-stu-id="f4344-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
