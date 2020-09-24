---
title: Licznik liczby elementów w sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164353"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="70e39-102">Licznik liczby elementów w sekwencji</span><span class="sxs-lookup"><span data-stu-id="70e39-102">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="70e39-103">Użyj <xref:System.Linq.Enumerable.Count%2A> operatora, aby policzyć liczbę elementów w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="70e39-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="70e39-104">Uruchomienie tego zapytania względem przykładowej bazy danych Northwind powoduje utworzenie danych wyjściowych `91` .</span><span class="sxs-lookup"><span data-stu-id="70e39-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e39-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="70e39-105">Example</span></span>  

 <span data-ttu-id="70e39-106">Poniższy przykład zlicza liczbę `Customers` w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="70e39-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="70e39-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="70e39-107">Example</span></span>  

 <span data-ttu-id="70e39-108">Poniższy przykład zlicza produkty w bazie danych, które nie zostały wycofane.</span><span class="sxs-lookup"><span data-stu-id="70e39-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="70e39-109">Uruchomienie tego przykładu w przypadku przykładowej bazy danych Northwind powoduje utworzenie danych wyjściowych `69` .</span><span class="sxs-lookup"><span data-stu-id="70e39-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="70e39-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70e39-110">See also</span></span>

- [<span data-ttu-id="70e39-111">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="70e39-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="70e39-112">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="70e39-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
