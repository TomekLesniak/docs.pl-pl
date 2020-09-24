---
title: 'Instrukcje: Zapytanie dotyczące informacji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166407"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="4f6bd-102">Instrukcje: Zapytanie dotyczące informacji</span><span class="sxs-lookup"><span data-stu-id="4f6bd-102">How to: Query for Information</span></span>

<span data-ttu-id="4f6bd-103">Zapytania w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] używają tej samej składni co zapytania w LINQ.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="4f6bd-104">Jedyną różnicą jest to, że obiekty, do których odwołują się [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytania, są mapowane na elementy w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="4f6bd-105">Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4f6bd-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4f6bd-106">tłumaczy zapytania zapisane w równoważne zapytania SQL i wysyła je do serwera w celu przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="4f6bd-107">Niektóre funkcje zapytań LINQ mogą wymagać specjalnej uwagi w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="4f6bd-108">Aby uzyskać więcej informacji, zobacz [pojęcia dotyczące zapytań](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="4f6bd-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f6bd-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="4f6bd-109">Example</span></span>  

 <span data-ttu-id="4f6bd-110">Poniższe zapytanie pyta o listę klientów z usługi Londyn.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="4f6bd-111">W tym przykładzie `Customers` jest to tabela w przykładowej bazie danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="4f6bd-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4f6bd-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4f6bd-112">See also</span></span>

- [<span data-ttu-id="4f6bd-113">Tworzenie modelu obiektu</span><span class="sxs-lookup"><span data-stu-id="4f6bd-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="4f6bd-114">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="4f6bd-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="4f6bd-115">wykonywanie zapytania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="4f6bd-115">Querying the Database</span></span>](querying-the-database.md)
