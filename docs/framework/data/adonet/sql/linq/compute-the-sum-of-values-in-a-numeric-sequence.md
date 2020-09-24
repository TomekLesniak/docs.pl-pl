---
title: Obliczanie sumy wartości w sekwencji numerycznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3d160e2cce5f3e0a7eea305657260b6fa4ded7fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164444"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a><span data-ttu-id="7513a-102">Obliczanie sumy wartości w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="7513a-102">Compute the Sum of Values in a Numeric Sequence</span></span>

<span data-ttu-id="7513a-103">Użyj <xref:System.Linq.Enumerable.Sum%2A> operatora, aby obliczyć sumę wartości liczbowych w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="7513a-103">Use the <xref:System.Linq.Enumerable.Sum%2A> operator to compute the sum of numeric values in a sequence.</span></span>  
  
 <span data-ttu-id="7513a-104">Zwróć uwagę na następujące cechy `Sum` operatora w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="7513a-104">Note the following characteristics of the `Sum` operator in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="7513a-105">Operator agregujący standardowego operatora zapytania `Sum` ma wartość zero dla pustej sekwencji lub sekwencji zawierającej tylko wartości null.</span><span class="sxs-lookup"><span data-stu-id="7513a-105">The Standard Query Operator aggregate operator `Sum` evaluates to zero for an empty sequence or a sequence that contains only nulls.</span></span> <span data-ttu-id="7513a-106">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] semantyka SQL pozostaje niezmieniona.</span><span class="sxs-lookup"><span data-stu-id="7513a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged.</span></span> <span data-ttu-id="7513a-107">Z tego powodu program `Sum` zwraca wartość null zamiast zero dla pustej sekwencji lub dla sekwencji zawierającej tylko wartości null.</span><span class="sxs-lookup"><span data-stu-id="7513a-107">For this reason, `Sum` evaluates to null instead of to zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
- <span data-ttu-id="7513a-108">Ograniczenia SQL dotyczące wyników pośrednich stosują się do agregacji w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7513a-108">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="7513a-109">Suma 32-bitowych liczb całkowitych nie jest obliczana przy użyciu 64-bitowych wyników, a przepełnienie może wystąpić w przypadku [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczenia `Sum` .</span><span class="sxs-lookup"><span data-stu-id="7513a-109">Sum of 32-bit integer quantities is not computed by using 64-bit results, and overflow can occur for the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Sum`.</span></span> <span data-ttu-id="7513a-110">Taka możliwość istnieje, nawet jeśli implementacja standardowego operatora zapytań nie powoduje przepełnienia odpowiedniej sekwencji w pamięci.</span><span class="sxs-lookup"><span data-stu-id="7513a-110">This possibility exists even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7513a-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="7513a-111">Example</span></span>  

 <span data-ttu-id="7513a-112">Poniższy przykład umożliwia znalezienie łącznego frachtu wszystkich zamówień w `Order` tabeli.</span><span class="sxs-lookup"><span data-stu-id="7513a-112">The following example finds the total freight of all orders in the `Order` table.</span></span>  
  
 <span data-ttu-id="7513a-113">W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `64942.6900` .</span><span class="sxs-lookup"><span data-stu-id="7513a-113">If you run this query against the Northwind sample database, the output is: `64942.6900`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="7513a-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="7513a-114">Example</span></span>  

 <span data-ttu-id="7513a-115">Poniższy przykład umożliwia znalezienie łącznej liczby jednostek w kolejności dla wszystkich produktów.</span><span class="sxs-lookup"><span data-stu-id="7513a-115">The following example finds the total number of units on order for all products.</span></span>  
  
 <span data-ttu-id="7513a-116">W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `780` .</span><span class="sxs-lookup"><span data-stu-id="7513a-116">If you run this query against the Northwind sample database, the output is: `780`.</span></span>  
  
 <span data-ttu-id="7513a-117">Należy zauważyć, że należy rzutować `short` typy (na przykład `UnitsOnOrder` ), ponieważ `Sum` nie ma przeciążenia dla krótkich typów.</span><span class="sxs-lookup"><span data-stu-id="7513a-117">Note that you must cast `short` types (for example, `UnitsOnOrder`) because `Sum` has no overload for short types.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="7513a-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7513a-118">See also</span></span>

- [<span data-ttu-id="7513a-119">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="7513a-119">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="7513a-120">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="7513a-120">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
