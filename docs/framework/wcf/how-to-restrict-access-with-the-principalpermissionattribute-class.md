---
title: 'Instrukcje: Ograniczanie dostępu przy użyciu klasy PrincipalPermissionAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: 92d27548c510a19bf36ffaffb532f48461146d99
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269616"
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="19778-102">Instrukcje: Ograniczanie dostępu przy użyciu klasy PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="19778-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>

<span data-ttu-id="19778-103">Kontrolowanie dostępu do zasobów na komputerze z domeną systemu Windows to podstawowe zadanie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="19778-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="19778-104">Na przykład tylko niektórzy użytkownicy powinni mieć możliwość wyświetlania poufnych danych, takich jak informacje o płacach.</span><span class="sxs-lookup"><span data-stu-id="19778-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="19778-105">W tym temacie wyjaśniono, jak ograniczyć dostęp do metody przez wymaganie, aby użytkownik należał do wstępnie zdefiniowanej grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="19778-106">Aby uzyskać przykład roboczy, zobacz [autoryzowanie dostępu do operacji usługi](./samples/authorizing-access-to-service-operations.md).</span><span class="sxs-lookup"><span data-stu-id="19778-106">For a working sample, see [Authorizing Access to Service Operations](./samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="19778-107">Zadanie składa się z dwóch oddzielnych procedur.</span><span class="sxs-lookup"><span data-stu-id="19778-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="19778-108">Najpierw tworzy grupę i wypełnia ją użytkownikami.</span><span class="sxs-lookup"><span data-stu-id="19778-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="19778-109">Drugi stosuje klasę, <xref:System.Security.Permissions.PrincipalPermissionAttribute> Aby określić grupę.</span><span class="sxs-lookup"><span data-stu-id="19778-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="19778-110">Aby utworzyć grupę systemu Windows</span><span class="sxs-lookup"><span data-stu-id="19778-110">To create a Windows group</span></span>  
  
1. <span data-ttu-id="19778-111">Otwórz konsolę **Zarządzanie komputerem** .</span><span class="sxs-lookup"><span data-stu-id="19778-111">Open the **Computer Management** console.</span></span>  
  
2. <span data-ttu-id="19778-112">Na panelu po lewej stronie kliknij pozycję **lokalni użytkownicy i grupy**.</span><span class="sxs-lookup"><span data-stu-id="19778-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3. <span data-ttu-id="19778-113">Kliknij prawym przyciskiem myszy pozycję **grupy**, a następnie kliknij pozycję **Nowa grupa**.</span><span class="sxs-lookup"><span data-stu-id="19778-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4. <span data-ttu-id="19778-114">W polu **Nazwa grupy** wpisz nazwę nowej grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5. <span data-ttu-id="19778-115">W polu **Opis** wpisz opis nowej grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-115">In the **Description** box, type a description of the new group.</span></span>  
  
6. <span data-ttu-id="19778-116">Kliknij przycisk **Dodaj** , aby dodać nowych członków do grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-116">Click the **Add** button to add new members to the group.</span></span>  
  
7. <span data-ttu-id="19778-117">Jeśli dodano Cię do grupy i chcesz przetestować Poniższy kod, musisz wylogować się z komputera i ponownie zalogować się do grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="19778-118">Na żądanie członkostwa użytkowników</span><span class="sxs-lookup"><span data-stu-id="19778-118">To demand user membership</span></span>  
  
1. <span data-ttu-id="19778-119">Otwórz plik kodu Windows Communication Foundation (WCF), który zawiera zaimplementowany kod kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="19778-119">Open the Windows Communication Foundation (WCF) code file that contains the implemented service contract code.</span></span> <span data-ttu-id="19778-120">Aby uzyskać więcej informacji na temat implementowania kontraktu, zobacz [implementowanie kontraktów usług](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="19778-120">For more information about implementing a contract, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="19778-121">Zastosuj <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybut do każdej metody, która musi być ograniczona do konkretnej grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="19778-122">Ustaw <xref:System.Security.Permissions.SecurityAttribute.Action%2A> Właściwość na <xref:System.Security.Permissions.SecurityAction.Demand> i <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> Właściwość na nazwę grupy.</span><span class="sxs-lookup"><span data-stu-id="19778-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="19778-123">Przykład:</span><span class="sxs-lookup"><span data-stu-id="19778-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="19778-124">W przypadku zastosowania <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybutu do kontraktu a <xref:System.Security.SecurityException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="19778-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="19778-125">Atrybut można zastosować tylko na poziomie metody.</span><span class="sxs-lookup"><span data-stu-id="19778-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="19778-126">Używanie certyfikatu w celu kontrolowania dostępu do metody</span><span class="sxs-lookup"><span data-stu-id="19778-126">Using a Certificate to Control Access to a Method</span></span>  

 <span data-ttu-id="19778-127">Można również użyć `PrincipalPermissionAttribute` klasy do kontroli dostępu do metody, jeśli typ poświadczeń klienta jest certyfikatem.</span><span class="sxs-lookup"><span data-stu-id="19778-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="19778-128">Aby to zrobić, musisz mieć podmiot certyfikatu i odcisk palca.</span><span class="sxs-lookup"><span data-stu-id="19778-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="19778-129">Aby sprawdzić certyfikat dla jego właściwości, zobacz [How to: View Certificates with MMC przystawka](./feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="19778-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](./feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="19778-130">Aby znaleźć wartość odcisku palca, zobacz [How to: Pobieranie odcisku palca certyfikatu](./feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="19778-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](./feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="19778-131">Aby kontrolować dostęp przy użyciu certyfikatu</span><span class="sxs-lookup"><span data-stu-id="19778-131">To control access using a certificate</span></span>  
  
1. <span data-ttu-id="19778-132">Zastosuj <xref:System.Security.Permissions.PrincipalPermissionAttribute> klasę do metody, do której chcesz ograniczyć dostęp.</span><span class="sxs-lookup"><span data-stu-id="19778-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2. <span data-ttu-id="19778-133">Ustaw akcję atrybutu na <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="19778-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3. <span data-ttu-id="19778-134">Ustaw `Name` Właściwość na ciąg, który składa się z nazwy podmiotu i odcisku palca certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="19778-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="19778-135">Rozdziel dwie wartości średnikami i spacjami, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="19778-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4. <span data-ttu-id="19778-136">Ustaw <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Właściwość na <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> tak, jak pokazano w następującym przykładzie konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="19778-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="19778-137">Ustawienie tej wartości `UseAspNetRoles` wskazuje, że `Name` Właściwość `PrincipalPermissionAttribute` zostanie użyta do przeprowadzenia porównania ciągów.</span><span class="sxs-lookup"><span data-stu-id="19778-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="19778-138">Jeśli certyfikat jest używany jako poświadczenie klienta, domyślnie program WCF łączy nazwę pospolitą certyfikatu i odcisk palca z średnikiem, aby utworzyć unikatową wartość dla podstawowej tożsamości klienta.</span><span class="sxs-lookup"><span data-stu-id="19778-138">When a certificate is used as a client credential, by default WCF concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="19778-139">W przypadku `UseAspNetRoles` Ustawienia jako `PrincipalPermissionMode` dla usługi ta podstawowa wartość tożsamości jest porównywana z `Name` wartością właściwości w celu określenia praw dostępu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="19778-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="19778-140">Alternatywnie, podczas tworzenia usługi samodzielnej, należy ustawić <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Właściwość w kodzie, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="19778-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="19778-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="19778-141">See also</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.SecurityAction.Demand>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>
- [<span data-ttu-id="19778-142">Autoryzowanie dostępu do operacji usługi</span><span class="sxs-lookup"><span data-stu-id="19778-142">Authorizing Access to Service Operations</span></span>](./samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="19778-143">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="19778-143">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="19778-144">Implementowanie kontraktów usług</span><span class="sxs-lookup"><span data-stu-id="19778-144">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
