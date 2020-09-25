---
title: Zdalne a lokalne wykonanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: c99e726902192fc8324e77441b80aa4519c55ddc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196952"
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="c9f10-102">Zdalne a lokalne wykonanie</span><span class="sxs-lookup"><span data-stu-id="c9f10-102">Remote vs. Local Execution</span></span>

<span data-ttu-id="c9f10-103">Możesz zdecydować się na zdalne wykonywanie zapytań (to oznacza, że aparat bazy danych wykonuje zapytanie względem bazy danych) lub lokalnie ( [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wykonuje zapytanie względem lokalnej pamięci podręcznej).</span><span class="sxs-lookup"><span data-stu-id="c9f10-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="c9f10-104">Zdalne wykonywanie kodu</span><span class="sxs-lookup"><span data-stu-id="c9f10-104">Remote Execution</span></span>  

 <span data-ttu-id="c9f10-105">Rozpatrzmy następujące zapytanie:</span><span class="sxs-lookup"><span data-stu-id="c9f10-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="c9f10-106">Jeśli baza danych ma tysiące rzędów zamówień, nie chcesz pobierać ich wszystkich, aby przetwarzać mały podzestaw.</span><span class="sxs-lookup"><span data-stu-id="c9f10-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="c9f10-107">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.EntitySet%601> Klasa implementuje <xref:System.Linq.IQueryable> interfejs.</span><span class="sxs-lookup"><span data-stu-id="c9f10-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="c9f10-108">Takie podejście gwarantuje, że takie zapytania można wykonać zdalnie.</span><span class="sxs-lookup"><span data-stu-id="c9f10-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="c9f10-109">Przepływ dwóch głównych korzyści z tej techniki:</span><span class="sxs-lookup"><span data-stu-id="c9f10-109">Two major benefits flow from this technique:</span></span>  
  
- <span data-ttu-id="c9f10-110">Nie pobrano zbędnych danych.</span><span class="sxs-lookup"><span data-stu-id="c9f10-110">Unnecessary data is not retrieved.</span></span>  
  
- <span data-ttu-id="c9f10-111">Zapytanie wykonywane przez aparat bazy danych jest często wydajniejsze ze względu na indeksy bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c9f10-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="c9f10-112">lokalne wykonanie</span><span class="sxs-lookup"><span data-stu-id="c9f10-112">Local Execution</span></span>  

 <span data-ttu-id="c9f10-113">W innych sytuacjach może być konieczne posiadanie kompletnego zestawu powiązanych jednostek w lokalnej pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="c9f10-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="c9f10-114">W tym celu <xref:System.Data.Linq.EntitySet%601> zapewnia metodę, <xref:System.Data.Linq.EntitySet%601.Load%2A> Aby jawnie załadować wszystkie elementy członkowskie <xref:System.Data.Linq.EntitySet%601> .</span><span class="sxs-lookup"><span data-stu-id="c9f10-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="c9f10-115">Jeśli <xref:System.Data.Linq.EntitySet%601> jest już załadowany, kolejne zapytania są wykonywane lokalnie.</span><span class="sxs-lookup"><span data-stu-id="c9f10-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="c9f10-116">To podejście jest pomocne na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="c9f10-116">This approach helps in two ways:</span></span>  
  
- <span data-ttu-id="c9f10-117">Jeśli kompletny zestaw musi być używany lokalnie lub wiele razy, można uniknąć zdalnych zapytań i skojarzonych opóźnień.</span><span class="sxs-lookup"><span data-stu-id="c9f10-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
- <span data-ttu-id="c9f10-118">Jednostkę można serializować jako kompletną jednostkę.</span><span class="sxs-lookup"><span data-stu-id="c9f10-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="c9f10-119">Poniższy fragment kodu ilustruje sposób uzyskania lokalnego wykonania:</span><span class="sxs-lookup"><span data-stu-id="c9f10-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="c9f10-120">Porównanie</span><span class="sxs-lookup"><span data-stu-id="c9f10-120">Comparison</span></span>  

 <span data-ttu-id="c9f10-121">Te dwie możliwości oferują zaawansowaną kombinację opcji: zdalne wykonywanie dużych kolekcji i wykonywanie lokalne dla małych kolekcji lub, gdzie jest wymagana kompletna kolekcja.</span><span class="sxs-lookup"><span data-stu-id="c9f10-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="c9f10-122">Implementowanie zdalnego wykonywania przez <xref:System.Linq.IQueryable> program i wykonywanie lokalne w odniesieniu do <xref:System.Collections.Generic.IEnumerable%601> kolekcji w pamięci.</span><span class="sxs-lookup"><span data-stu-id="c9f10-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="c9f10-123">Aby wymusić wykonanie lokalne (czyli <xref:System.Collections.Generic.IEnumerable%601> ), zobacz [konwertowanie typu na rodzajowy interfejs IEnumerable](convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="c9f10-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="c9f10-124">Zapytania dotyczące nieuporządkowanych zestawów</span><span class="sxs-lookup"><span data-stu-id="c9f10-124">Queries Against Unordered Sets</span></span>  

 <span data-ttu-id="c9f10-125">Należy zwrócić uwagę na istotną różnicę między lokalną kolekcją, która implementuje <xref:System.Collections.Generic.List%601> i kolekcję, która zapewnia zapytania zdalne wykonywane w odniesieniu do *nieuporządkowanych zestawów* w relacyjnej bazie danych.</span><span class="sxs-lookup"><span data-stu-id="c9f10-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <span data-ttu-id="c9f10-126"><xref:System.Collections.Generic.List%601> metody, takie jak te, które używają wartości indeksu, wymagają semantyki list, która zazwyczaj nie można uzyskać za pomocą zapytania zdalnego dla nieuporządkowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="c9f10-126"><xref:System.Collections.Generic.List%601> methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="c9f10-127">Z tego powodu takie metody niejawnie ładują, <xref:System.Data.Linq.EntitySet%601> Aby umożliwić wykonanie lokalne.</span><span class="sxs-lookup"><span data-stu-id="c9f10-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f10-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c9f10-128">See also</span></span>

- [<span data-ttu-id="c9f10-129">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="c9f10-129">Query Concepts</span></span>](query-concepts.md)
