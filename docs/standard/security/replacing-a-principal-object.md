---
title: Zastępowanie obiektu głównego
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: b8f7a8fbd3b9c65126d6a3a65a5f6722f2ad93de
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824177"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="3cff8-102">Zastępowanie obiektu głównego</span><span class="sxs-lookup"><span data-stu-id="3cff8-102">Replacing a Principal Object</span></span>

<span data-ttu-id="3cff8-103">Aplikacje, które zapewniają usługi uwierzytelniania, muszą być w stanie zastąpić obiekt **podmiotu zabezpieczeń** ( <xref:System.Security.Principal.IPrincipal> ) dla danego wątku.</span><span class="sxs-lookup"><span data-stu-id="3cff8-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="3cff8-104">Ponadto system zabezpieczeń musi pomagać w ochronie możliwości zastąpienia obiektów **głównych** , ponieważ złośliwie podłączona, nieprawidłowa **podmiot** zabezpieczeń narusza zabezpieczenia aplikacji przez zajęcie nieprawdziwej tożsamością lub rolą.</span><span class="sxs-lookup"><span data-stu-id="3cff8-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="3cff8-105">W związku z tym aplikacje, które wymagają możliwości zastąpienia obiektów **Principal** , muszą mieć przyznany <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> obiekt dla kontroli podmiotu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="3cff8-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="3cff8-106">(Należy zauważyć, że to uprawnienie nie jest wymagane do wykonywania kontroli zabezpieczeń opartych na rolach ani do tworzenia obiektów **głównych** ).</span><span class="sxs-lookup"><span data-stu-id="3cff8-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
<span data-ttu-id="3cff8-107">Bieżący obiekt **Principal** można zastąpić, wykonując następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="3cff8-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="3cff8-108">Utwórz zastępujący obiekt **podmiotu zabezpieczeń** i skojarzony obiekt **tożsamości** .</span><span class="sxs-lookup"><span data-stu-id="3cff8-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2. <span data-ttu-id="3cff8-109">Dołącz nowy obiekt **Principal** do kontekstu wywołania.</span><span class="sxs-lookup"><span data-stu-id="3cff8-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cff8-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="3cff8-110">Example</span></span>

<span data-ttu-id="3cff8-111">Poniższy przykład pokazuje, jak utworzyć ogólny obiekt główny i używać go do ustawiania podmiotu zabezpieczeń wątku.</span><span class="sxs-lookup"><span data-stu-id="3cff8-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3cff8-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3cff8-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [<span data-ttu-id="3cff8-113">Obiekty główne i obiekty tożsamości</span><span class="sxs-lookup"><span data-stu-id="3cff8-113">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="3cff8-114">Zabezpieczenia ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3cff8-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
