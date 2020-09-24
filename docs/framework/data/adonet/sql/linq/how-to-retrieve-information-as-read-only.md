---
title: 'Instrukcje: Pobieranie informacji jako tylko do odczytu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 0a6853ef5d0b67e5efb95731adb5a106e8701e0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155838"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="b3ac6-102">Instrukcje: Pobieranie informacji jako tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="b3ac6-102">How to: Retrieve Information As Read-Only</span></span>

<span data-ttu-id="b3ac6-103">Jeśli nie zamierzasz zmieniać danych, możesz zwiększyć wydajność zapytań, wyszukując wyniki tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="b3ac6-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="b3ac6-104">Przetwarzanie w trybie tylko do odczytu jest implementowane przez ustawienie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> do `false` .</span><span class="sxs-lookup"><span data-stu-id="b3ac6-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3ac6-105">Gdy <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> jest ustawiona na `false` , <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> jest niejawnie ustawiona na `false` .</span><span class="sxs-lookup"><span data-stu-id="b3ac6-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3ac6-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="b3ac6-106">Example</span></span>  

 <span data-ttu-id="b3ac6-107">Poniższy kod pobiera kolekcję dat zatrudnienia pracowników w trybie tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="b3ac6-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b3ac6-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b3ac6-108">See also</span></span>

- [<span data-ttu-id="b3ac6-109">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="b3ac6-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="b3ac6-110">wykonywanie zapytania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="b3ac6-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="b3ac6-111">Odroczone a bezpośrednie ładowanie</span><span class="sxs-lookup"><span data-stu-id="b3ac6-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
