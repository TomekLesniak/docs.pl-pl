---
title: 'Instrukcje: Filtrowanie powiązanych danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e12bab55b03fac3383b98b8ee1c56ab1954ff978
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173461"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="66a64-102">Instrukcje: Filtrowanie powiązanych danych</span><span class="sxs-lookup"><span data-stu-id="66a64-102">How to: Filter Related Data</span></span>

<span data-ttu-id="66a64-103">Użyj <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> metody, aby określić podzapytania, aby ograniczyć ilość pobranych danych.</span><span class="sxs-lookup"><span data-stu-id="66a64-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66a64-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="66a64-104">Example</span></span>  

 <span data-ttu-id="66a64-105">W poniższym przykładzie <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> Metoda ogranicza `Orders` pobrane elementy do tych, które nie zostały wysłane dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="66a64-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="66a64-106">Bez tego podejścia wszystkie `Orders` zostałyby pobrane, nawet jeśli pożądane jest tylko podzbiór.</span><span class="sxs-lookup"><span data-stu-id="66a64-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="66a64-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="66a64-107">See also</span></span>

- [<span data-ttu-id="66a64-108">wykonywanie zapytania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="66a64-108">Querying the Database</span></span>](querying-the-database.md)
