---
title: 'Instrukcje: Tworzenie obiektu WindowsPrincipal'
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET], creating a WindowsPrincipal object
- security [.NET], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
ms.openlocfilehash: d4140470308a09774e5e4eee429c1e91b559d063
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819035"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="2cac3-102">Instrukcje: Tworzenie obiektu WindowsPrincipal</span><span class="sxs-lookup"><span data-stu-id="2cac3-102">How to: Create a WindowsPrincipal Object</span></span>

> [!NOTE]
> <span data-ttu-id="2cac3-103">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2cac3-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="2cac3-104">Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core Security](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="2cac3-104">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="2cac3-105">Istnieją dwa sposoby tworzenia <xref:System.Security.Principal.WindowsPrincipal> obiektu, w zależności od tego, czy kod musi wielokrotnie wykonywać walidację opartą na rolach, czy też musi wykonać tę operację tylko raz.</span><span class="sxs-lookup"><span data-stu-id="2cac3-105">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
<span data-ttu-id="2cac3-106">Jeśli kod musi wielokrotnie wykonywać walidację opartą na rolach, pierwsze z poniższych procedur generuje mniej kosztów.</span><span class="sxs-lookup"><span data-stu-id="2cac3-106">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="2cac3-107">Gdy kod musi wprowadzać walidacje oparte na rolach tylko raz, można utworzyć <xref:System.Security.Principal.WindowsPrincipal> Obiekt przy użyciu drugiego z poniższych procedur.</span><span class="sxs-lookup"><span data-stu-id="2cac3-107">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="2cac3-108">Aby utworzyć obiekt WindowsPrincipal do powtarzanej walidacji</span><span class="sxs-lookup"><span data-stu-id="2cac3-108">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1. <span data-ttu-id="2cac3-109">Wywołaj <xref:System.AppDomain.SetPrincipalPolicy%2A> metodę dla <xref:System.AppDomain> obiektu, który jest zwracany przez właściwość statyczną <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> , przekazując metodę <xref:System.Security.Principal.PrincipalPolicy> wartości wyliczenia, która wskazuje, jakie nowe zasady powinny być.</span><span class="sxs-lookup"><span data-stu-id="2cac3-109">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="2cac3-110">Obsługiwane wartości to <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal> , <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> , i <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal> .</span><span class="sxs-lookup"><span data-stu-id="2cac3-110">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="2cac3-111">Poniższy kod ilustruje to wywołanie metody.</span><span class="sxs-lookup"><span data-stu-id="2cac3-111">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2. <span data-ttu-id="2cac3-112">Za pomocą zestawu zasad należy użyć właściwości statycznej <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> do pobrania podmiotu zabezpieczeń, który hermetyzuje bieżącego użytkownika systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2cac3-112">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="2cac3-113">Ponieważ typem zwracanym właściwości jest <xref:System.Security.Principal.IPrincipal> , należy rzutować wynik na <xref:System.Security.Principal.WindowsPrincipal> Typ.</span><span class="sxs-lookup"><span data-stu-id="2cac3-113">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="2cac3-114">Poniższy kod inicjuje nowy <xref:System.Security.Principal.WindowsPrincipal> obiekt do wartości podmiotu zabezpieczeń skojarzonego z bieżącym wątkiem.</span><span class="sxs-lookup"><span data-stu-id="2cac3-114">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal =
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim myPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)
    ```  
  
3. <span data-ttu-id="2cac3-115">Po utworzeniu obiektu podmiotu zabezpieczeń można użyć jednej z kilku metod weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="2cac3-115">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="2cac3-116">Aby utworzyć obiekt WindowsPrincipal na potrzeby pojedynczej walidacji</span><span class="sxs-lookup"><span data-stu-id="2cac3-116">To create a WindowsPrincipal object for a single validation</span></span>  
  
1. <span data-ttu-id="2cac3-117">Zainicjuj nowy <xref:System.Security.Principal.WindowsIdentity> obiekt przez wywołanie metody statycznej <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> , która wysyła zapytanie do bieżącego konta systemu Windows i umieszcza informacje o tym koncie w nowo utworzonym obiekcie tożsamości.</span><span class="sxs-lookup"><span data-stu-id="2cac3-117">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="2cac3-118">Poniższy kod tworzy nowy <xref:System.Security.Principal.WindowsIdentity> obiekt i inicjuje go dla bieżącego uwierzytelnionego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2cac3-118">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity myIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim myIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2. <span data-ttu-id="2cac3-119">Utwórz nowy <xref:System.Security.Principal.WindowsPrincipal> obiekt i przekaż go do wartości <xref:System.Security.Principal.WindowsIdentity> obiektu utworzonego w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="2cac3-119">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal = new WindowsPrincipal(myIdentity);  
    ```  
  
    ```vb  
    Dim myPrincipal As New WindowsPrincipal(myIdentity)  
    ```  
  
3. <span data-ttu-id="2cac3-120">Po utworzeniu obiektu podmiotu zabezpieczeń można użyć jednej z kilku metod weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="2cac3-120">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cac3-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2cac3-121">See also</span></span>

- [<span data-ttu-id="2cac3-122">Obiekty główne i obiekty tożsamości</span><span class="sxs-lookup"><span data-stu-id="2cac3-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="2cac3-123">Zabezpieczenia ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2cac3-123">ASP.NET Core Security</span></span>](/aspnet/core/security/)
