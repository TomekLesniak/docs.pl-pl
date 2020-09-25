---
title: 'Instrukcje: Wyłączanie odroczonego ładowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196965"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="12b5f-102">Instrukcje: Wyłączanie odroczonego ładowania</span><span class="sxs-lookup"><span data-stu-id="12b5f-102">How to: Turn Off Deferred Loading</span></span>

<span data-ttu-id="12b5f-103">Można wyłączyć odroczone ładowanie według ustawienia <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> do `false` .</span><span class="sxs-lookup"><span data-stu-id="12b5f-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="12b5f-104">Aby uzyskać więcej informacji, zobacz [odroczone względem natychmiastowego ładowania](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="12b5f-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12b5f-105">Ładowanie odroczone jest wyłączone przez implikację, gdy śledzenie obiektów jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="12b5f-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="12b5f-106">Aby uzyskać więcej informacji, zobacz [jak: pobrać informacje jako tylko do odczytu](how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="12b5f-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12b5f-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="12b5f-107">Example</span></span>  

 <span data-ttu-id="12b5f-108">Poniższy przykład pokazuje, jak wyłączyć odroczone ładowanie przez ustawienie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> do `false` .</span><span class="sxs-lookup"><span data-stu-id="12b5f-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="12b5f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="12b5f-109">See also</span></span>

- [<span data-ttu-id="12b5f-110">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="12b5f-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="12b5f-111">wykonywanie zapytania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="12b5f-111">Querying the Database</span></span>](querying-the-database.md)
