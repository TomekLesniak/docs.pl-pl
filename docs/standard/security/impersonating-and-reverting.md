---
title: Personifikacja i przywracanie
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 7eecc7d6cb3fa4cc1c1bd971d36f9d3ca47a7144
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555682"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="e3aa4-102">Personifikacja i przywracanie</span><span class="sxs-lookup"><span data-stu-id="e3aa4-102">Impersonating and Reverting</span></span>

> [!NOTE]
> <span data-ttu-id="e3aa4-103">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="e3aa4-104">Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core Security](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="e3aa4-104">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="e3aa4-105">Czasami może być konieczne uzyskanie tokenu konta systemu Windows w celu personifikacji konta systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-105">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="e3aa4-106">Na przykład aplikacja oparta na ASP.NET może wymagać działania w imieniu kilku użytkowników w różnym czasie.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-106">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="e3aa4-107">Aplikacja może zaakceptować token, który reprezentuje administratora Internet Information Services (IIS), spersonifikować tego użytkownika, wykonać operację i przywrócić poprzednią tożsamość.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-107">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="e3aa4-108">Następnie może zaakceptować token z usług IIS, który reprezentuje użytkownika o mniejszej liczbie praw, wykonanie jakiejś operacji i przywrócenie.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-108">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="e3aa4-109">W sytuacjach, w których aplikacja musi personifikować konto systemu Windows, które nie zostało dołączone do bieżącego wątku przez usługi IIS, należy pobrać token tego konta i użyć go w celu aktywowania konta.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-109">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="e3aa4-110">Można to zrobić, wykonując następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="e3aa4-110">You can do this by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="e3aa4-111">Pobierz token konta dla określonego użytkownika, wykonując wywołanie do niezarządzanej metody **funkcji LogonUser** .</span><span class="sxs-lookup"><span data-stu-id="e3aa4-111">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="e3aa4-112">Ta metoda nie znajduje się w bibliotece klas bazowych .NET, ale znajduje się w niezarządzanej **advapi32.dll**.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-112">This method is not in the .NET base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="e3aa4-113">Uzyskiwanie dostępu do metod w kodzie niezarządzanym jest operacją zaawansowaną i wykracza poza zakres tej dyskusji.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-113">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="e3aa4-114">Aby uzyskać więcej informacji, zobacz [współdziałanie z kodem niezarządzanym](../../framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3aa4-114">For more information, see [Interoperating with Unmanaged Code](../../framework/interop/index.md).</span></span> <span data-ttu-id="e3aa4-115">Aby uzyskać więcej informacji na temat metody **funkcji LogonUser** i **advapi32.dll**, zobacz dokumentację zestawu SDK platformy.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-115">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2. <span data-ttu-id="e3aa4-116">Utwórz nowe wystąpienie klasy **WindowsIdentity** , przekazując token.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-116">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="e3aa4-117">Poniższy kod ilustruje to wywołanie, gdzie `hToken` reprezentuje token systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-117">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. <span data-ttu-id="e3aa4-118">Rozpocznij personifikację, tworząc nowe wystąpienie <xref:System.Security.Principal.WindowsImpersonationContext> klasy i inicjując je za pomocą <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> metody zainicjowanej klasy, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-118">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. <span data-ttu-id="e3aa4-119">Gdy nie ma już potrzeby personifikacji, wywołaj <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> metodę, aby przywrócić personifikację, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-119">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="e3aa4-120">Jeśli zaufany kod przyłączył już <xref:System.Security.Principal.WindowsPrincipal> obiekt do wątku, można wywołać metodę **personifikacji**metody wystąpienia, która nie przyjmuje tokenu konta.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-120">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="e3aa4-121">Należy zauważyć, że jest to przydatne tylko wtedy, gdy obiekt **WindowsPrincipal** na wątku reprezentuje użytkownika innego niż ten, w którym proces jest aktualnie wykonywany.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-121">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="e3aa4-122">Na przykład może wystąpić taka sytuacja przy użyciu ASP.NET z włączonym uwierzytelnianiem systemu Windows, a Personifikacja jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-122">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="e3aa4-123">W takim przypadku proces jest uruchamiany na koncie skonfigurowanym w Internet Information Services (IIS), podczas gdy bieżący podmiot zabezpieczeń reprezentuje użytkownika systemu Windows, który uzyskuje dostęp do strony.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-123">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="e3aa4-124">Należy pamiętać, że nie **Personifikuj** ani **Cofaj** zmiany obiektu **podmiotu zabezpieczeń** ( <xref:System.Security.Principal.IPrincipal> ) skojarzonego z bieżącym kontekstem wywołania.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-124">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="e3aa4-125">Zamiast tego personifikacja i wycofywanie zmienia token skojarzony z bieżącym procesem systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e3aa4-125">Rather, impersonation and reverting change the token associated with the current operating system process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3aa4-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3aa4-126">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [<span data-ttu-id="e3aa4-127">Obiekty główne i obiekty tożsamości</span><span class="sxs-lookup"><span data-stu-id="e3aa4-127">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="e3aa4-128">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="e3aa4-128">Interoperating with Unmanaged Code</span></span>](../../framework/interop/index.md)
- [<span data-ttu-id="e3aa4-129">Zabezpieczenia ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3aa4-129">ASP.NET Core Security</span></span>](/aspnet/core/security/)
