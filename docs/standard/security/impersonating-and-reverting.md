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
# <a name="impersonating-and-reverting"></a>Personifikacja i przywracanie

> [!NOTE]
> Ten artykuł dotyczy systemu Windows.
>
> Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core Security](/aspnet/core/security/).

Czasami może być konieczne uzyskanie tokenu konta systemu Windows w celu personifikacji konta systemu Windows. Na przykład aplikacja oparta na ASP.NET może wymagać działania w imieniu kilku użytkowników w różnym czasie. Aplikacja może zaakceptować token, który reprezentuje administratora Internet Information Services (IIS), spersonifikować tego użytkownika, wykonać operację i przywrócić poprzednią tożsamość. Następnie może zaakceptować token z usług IIS, który reprezentuje użytkownika o mniejszej liczbie praw, wykonanie jakiejś operacji i przywrócenie.  
  
 W sytuacjach, w których aplikacja musi personifikować konto systemu Windows, które nie zostało dołączone do bieżącego wątku przez usługi IIS, należy pobrać token tego konta i użyć go w celu aktywowania konta. Można to zrobić, wykonując następujące zadania:  
  
1. Pobierz token konta dla określonego użytkownika, wykonując wywołanie do niezarządzanej metody **funkcji LogonUser** . Ta metoda nie znajduje się w bibliotece klas bazowych .NET, ale znajduje się w niezarządzanej **advapi32.dll**. Uzyskiwanie dostępu do metod w kodzie niezarządzanym jest operacją zaawansowaną i wykracza poza zakres tej dyskusji. Aby uzyskać więcej informacji, zobacz [współdziałanie z kodem niezarządzanym](../../framework/interop/index.md). Aby uzyskać więcej informacji na temat metody **funkcji LogonUser** i **advapi32.dll**, zobacz dokumentację zestawu SDK platformy.  
  
2. Utwórz nowe wystąpienie klasy **WindowsIdentity** , przekazując token. Poniższy kod ilustruje to wywołanie, gdzie `hToken` reprezentuje token systemu Windows.  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. Rozpocznij personifikację, tworząc nowe wystąpienie <xref:System.Security.Principal.WindowsImpersonationContext> klasy i inicjując je za pomocą <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> metody zainicjowanej klasy, jak pokazano w poniższym kodzie.  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. Gdy nie ma już potrzeby personifikacji, wywołaj <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> metodę, aby przywrócić personifikację, jak pokazano w poniższym kodzie.  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 Jeśli zaufany kod przyłączył już <xref:System.Security.Principal.WindowsPrincipal> obiekt do wątku, można wywołać metodę **personifikacji**metody wystąpienia, która nie przyjmuje tokenu konta. Należy zauważyć, że jest to przydatne tylko wtedy, gdy obiekt **WindowsPrincipal** na wątku reprezentuje użytkownika innego niż ten, w którym proces jest aktualnie wykonywany. Na przykład może wystąpić taka sytuacja przy użyciu ASP.NET z włączonym uwierzytelnianiem systemu Windows, a Personifikacja jest wyłączona. W takim przypadku proces jest uruchamiany na koncie skonfigurowanym w Internet Information Services (IIS), podczas gdy bieżący podmiot zabezpieczeń reprezentuje użytkownika systemu Windows, który uzyskuje dostęp do strony.  
  
 Należy pamiętać, że nie **Personifikuj** ani **Cofaj** zmiany obiektu **podmiotu zabezpieczeń** ( <xref:System.Security.Principal.IPrincipal> ) skojarzonego z bieżącym kontekstem wywołania. Zamiast tego personifikacja i wycofywanie zmienia token skojarzony z bieżącym procesem systemu operacyjnego.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Obiekty główne i obiekty tożsamości](principal-and-identity-objects.md)
- [Współdziałanie z kodem niezarządzanym](../../framework/interop/index.md)
- [Zabezpieczenia ASP.NET Core](/aspnet/core/security/)
