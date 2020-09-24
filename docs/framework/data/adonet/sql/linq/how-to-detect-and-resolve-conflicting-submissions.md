---
title: 'Instrukcje: Wykrywanie i rozwiązywanie powodujących konflikt przesłań'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147726"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="b145b-102">Instrukcje: Wykrywanie i rozwiązywanie powodujących konflikt przesłań</span><span class="sxs-lookup"><span data-stu-id="b145b-102">How to: Detect and Resolve Conflicting Submissions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b145b-103">oferuje wiele zasobów do wykrywania i rozwiązywania konfliktów, które pochodzą od zmian wielu użytkowników w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="b145b-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="b145b-104">Aby uzyskać więcej informacji, zobacz [How to: Manage konflikts Change](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="b145b-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b145b-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="b145b-105">Example</span></span>  

 <span data-ttu-id="b145b-106">Poniższy przykład pokazuje `try` / `catch` blok, który przechwytuje <xref:System.Data.Linq.ChangeConflictException> wyjątek.</span><span class="sxs-lookup"><span data-stu-id="b145b-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="b145b-107">Informacje o jednostkach i elementach członkowskich dla każdego konfliktu są wyświetlane w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="b145b-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b145b-108">Musisz dołączyć `using System.Reflection` dyrektywę ( `Imports System.Reflection` w Visual Basic) do obsługi pobierania informacji.</span><span class="sxs-lookup"><span data-stu-id="b145b-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="b145b-109">Aby uzyskać więcej informacji, zobacz <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="b145b-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b145b-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b145b-110">See also</span></span>

- [<span data-ttu-id="b145b-111">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="b145b-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="b145b-112">Instrukcje: Zarządzanie konfliktami zmian</span><span class="sxs-lookup"><span data-stu-id="b145b-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
