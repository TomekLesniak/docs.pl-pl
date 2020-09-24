---
title: Odnajdywanie wartości minimalnej w sekwencji numerycznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 2ffff8b69839d5c1e70e81f9fc6f3a97f57ac6c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155981"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="9c834-102">Odnajdywanie wartości minimalnej w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="9c834-102">Find the Minimum Value in a Numeric Sequence</span></span>

<span data-ttu-id="9c834-103">Użyj <xref:System.Linq.Enumerable.Min%2A> operatora, aby zwrócić minimalną wartość z sekwencji wartości liczbowych.</span><span class="sxs-lookup"><span data-stu-id="9c834-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c834-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="9c834-104">Example</span></span>  

 <span data-ttu-id="9c834-105">W poniższym przykładzie znajduje się najniższa cena jednostkowa dowolnego produktu.</span><span class="sxs-lookup"><span data-stu-id="9c834-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="9c834-106">W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `2.5000` .</span><span class="sxs-lookup"><span data-stu-id="9c834-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="9c834-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="9c834-107">Example</span></span>  

 <span data-ttu-id="9c834-108">Poniższy przykład umożliwia znalezienie najmniejszej ilości frachtu dla dowolnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="9c834-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="9c834-109">W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `0.0200` .</span><span class="sxs-lookup"><span data-stu-id="9c834-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9c834-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="9c834-110">Example</span></span>  

 <span data-ttu-id="9c834-111">W poniższym przykładzie jest używane minimum, aby znaleźć wartość `Products` , która ma najniższą cenę jednostkową w każdej kategorii.</span><span class="sxs-lookup"><span data-stu-id="9c834-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="9c834-112">Dane wyjściowe są uporządkowane według kategorii.</span><span class="sxs-lookup"><span data-stu-id="9c834-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="9c834-113">W przypadku uruchomienia poprzedniego zapytania względem przykładowej bazy danych Northwind wyniki będą wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="9c834-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="9c834-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9c834-114">See also</span></span>

- [<span data-ttu-id="9c834-115">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="9c834-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="9c834-116">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="9c834-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
