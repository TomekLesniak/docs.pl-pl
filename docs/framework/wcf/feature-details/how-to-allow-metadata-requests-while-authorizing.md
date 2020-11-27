---
title: 'Instrukcje: zezwalanie na żądania metadanych podczas autoryzowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 9acc007ea7837f7b8e6c958fa81547fe4fa5b2c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257616"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="227ae-102">Instrukcje: zezwalanie na żądania metadanych podczas autoryzowania</span><span class="sxs-lookup"><span data-stu-id="227ae-102">How To: Allow Metadata Requests While Authorizing</span></span>

<span data-ttu-id="227ae-103">W trakcie autoryzacji niestandardowej może być konieczne zezwolenie na przetworzenie żądania metadanych.</span><span class="sxs-lookup"><span data-stu-id="227ae-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="227ae-104">W poniższym temacie przedstawiono kroki umożliwiające zweryfikowanie takiego żądania.</span><span class="sxs-lookup"><span data-stu-id="227ae-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="227ae-105">Aby uzyskać więcej informacji na temat autoryzacji Windows Communication Foundation (WCF), zobacz [autoryzacja](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="227ae-105">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="227ae-106">Aby zezwolić na żądania metadanych podczas autoryzacji</span><span class="sxs-lookup"><span data-stu-id="227ae-106">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="227ae-107">Utwórz rozszerzenie <xref:System.ServiceModel.ServiceAuthorizationManager> klasy.</span><span class="sxs-lookup"><span data-stu-id="227ae-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="227ae-108">Zastąp <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="227ae-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="227ae-109">Metoda zwraca `true` lub `false` w zależności od tego, czy Autoryzacja jest dozwolona.</span><span class="sxs-lookup"><span data-stu-id="227ae-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="227ae-110">Informacje na temat bieżącej procedury znajdują się w <xref:System.ServiceModel.OperationContext> przekazaniu jako parametr do metody.</span><span class="sxs-lookup"><span data-stu-id="227ae-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="227ae-111">W przesłonięciu Sprawdź nazwę kontraktu, przestrzeń nazw i akcję, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="227ae-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="227ae-112">Jeśli warunki są prawidłowe, Wróć `true.`</span><span class="sxs-lookup"><span data-stu-id="227ae-112">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="227ae-113">Użyj punktu rozszerzalności, aby użyć klasy.</span><span class="sxs-lookup"><span data-stu-id="227ae-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="227ae-114">Aby uzyskać więcej informacji, zobacz [jak: Tworzenie niestandardowego Menedżera autoryzacji dla usługi](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="227ae-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="227ae-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="227ae-115">Example</span></span>  

 <span data-ttu-id="227ae-116">W poniższym przykładzie pokazano przesłonięcie <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="227ae-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="227ae-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="227ae-117">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="227ae-118">Autoryzacja</span><span class="sxs-lookup"><span data-stu-id="227ae-118">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="227ae-119">Zarządzanie oświadczeniami i autoryzacją za pomocą modelu tożsamości</span><span class="sxs-lookup"><span data-stu-id="227ae-119">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
