---
title: Odnajdywanie wartości maksymalnej w sekwencji numerycznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: b70b94338ca7bdbb600bac697d3a36ff117d757e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156007"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="41d53-102">Odnajdywanie wartości maksymalnej w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="41d53-102">Find the Maximum Value in a Numeric Sequence</span></span>

<span data-ttu-id="41d53-103">Użyj <xref:System.Linq.Enumerable.Max%2A> operatora, aby znaleźć najwyższą wartość w sekwencji wartości liczbowych.</span><span class="sxs-lookup"><span data-stu-id="41d53-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d53-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="41d53-104">Example</span></span>  

 <span data-ttu-id="41d53-105">Poniższy przykład umożliwia znalezienie najnowszej daty zatrudnienia dla każdego pracownika.</span><span class="sxs-lookup"><span data-stu-id="41d53-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="41d53-106">W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `11/15/1994 12:00:00 AM` .</span><span class="sxs-lookup"><span data-stu-id="41d53-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="41d53-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="41d53-107">Example</span></span>  

 <span data-ttu-id="41d53-108">Poniższy przykład znajduje najwięcej jednostek w magazynie dla każdego produktu.</span><span class="sxs-lookup"><span data-stu-id="41d53-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="41d53-109">W przypadku uruchomienia tego przykładu w przypadku przykładowej bazy danych Northwind dane wyjściowe to: `125` .</span><span class="sxs-lookup"><span data-stu-id="41d53-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="41d53-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="41d53-110">Example</span></span>  

 <span data-ttu-id="41d53-111">W poniższym przykładzie zastosowano wartość Max, aby znaleźć wartość `Products` , która ma najwyższą cenę jednostkową w każdej kategorii.</span><span class="sxs-lookup"><span data-stu-id="41d53-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="41d53-112">Następnie dane wyjściowe wyświetlają wyniki według kategorii.</span><span class="sxs-lookup"><span data-stu-id="41d53-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="41d53-113">W przypadku uruchomienia poprzedniego zapytania względem przykładowej bazy danych Northwind wyniki będą wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="41d53-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="41d53-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="41d53-114">See also</span></span>

- [<span data-ttu-id="41d53-115">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="41d53-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="41d53-116">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="41d53-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
