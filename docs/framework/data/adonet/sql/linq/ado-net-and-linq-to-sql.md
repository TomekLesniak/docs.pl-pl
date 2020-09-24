---
title: ADO.NET i LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 5dc1796b7fb7036f68c2435325c6a29d381c59f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161584"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="eb471-102">ADO.NET i LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eb471-102">ADO.NET and LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="eb471-103">jest częścią ADO.NETej technologii.</span><span class="sxs-lookup"><span data-stu-id="eb471-103">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="eb471-104">Jest on oparty na usługach oferowanych przez model dostawcy ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="eb471-104">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="eb471-105">W związku z tym możesz mieszać [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kod z istniejącymi aplikacjami ADO.NET i migrować bieżące rozwiązania ADO.NET do programu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb471-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="eb471-106">Poniższa ilustracja przedstawia ogólny widok relacji.</span><span class="sxs-lookup"><span data-stu-id="eb471-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="eb471-107">![LINQ to SQL i ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="eb471-107">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="eb471-108">Połączenia</span><span class="sxs-lookup"><span data-stu-id="eb471-108">Connections</span></span>  

 <span data-ttu-id="eb471-109">Podczas tworzenia programu można podać istniejące połączenie usługi ADO.NET [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="eb471-109">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="eb471-110">Wszystkie operacje związane z <xref:System.Data.Linq.DataContext> (łącznie z zapytaniami) używają tego podanego połączenia.</span><span class="sxs-lookup"><span data-stu-id="eb471-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="eb471-111">Jeśli połączenie jest już otwarte, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pozostawia je po zakończeniu pracy.</span><span class="sxs-lookup"><span data-stu-id="eb471-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="eb471-112">Zawsze możesz uzyskać dostęp do połączenia i zamknąć go samodzielnie przy użyciu <xref:System.Data.Linq.DataContext.Connection%2A> właściwości, jak w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="eb471-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="eb471-113">Transakcje</span><span class="sxs-lookup"><span data-stu-id="eb471-113">Transactions</span></span>  

 <span data-ttu-id="eb471-114">Możesz podać swoją <xref:System.Data.Linq.DataContext> własną transakcję bazy danych, gdy aplikacja już zainicjowała transakcję i chcesz, <xref:System.Data.Linq.DataContext> aby była ona używana.</span><span class="sxs-lookup"><span data-stu-id="eb471-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="eb471-115">Preferowaną metodą wykonywania transakcji z .NET Framework jest użycie <xref:System.Transactions.TransactionScope> obiektu.</span><span class="sxs-lookup"><span data-stu-id="eb471-115">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="eb471-116">Korzystając z tej metody, można tworzyć transakcje rozproszone, które działają między bazami danych i innymi menedżerami zasobów zamieszkałymi w pamięci.</span><span class="sxs-lookup"><span data-stu-id="eb471-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="eb471-117">Zakresy transakcji wymagają kilku zasobów do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="eb471-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="eb471-118">Promują się one tylko do transakcji rozproszonych, tylko gdy istnieje wiele połączeń w ramach transakcji.</span><span class="sxs-lookup"><span data-stu-id="eb471-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="eb471-119">Nie można użyć tej metody dla wszystkich baz danych.</span><span class="sxs-lookup"><span data-stu-id="eb471-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="eb471-120">Na przykład połączenie SqlClient nie może podwyższyć poziomu transakcji systemowych, gdy działa na serwerze SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="eb471-120">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="eb471-121">Zamiast tego automatycznie rejestrowana jest pełna, rozproszona transakcja, gdy widzi ona zakres transakcji, który jest używany.</span><span class="sxs-lookup"><span data-stu-id="eb471-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="eb471-122">Bezpośrednie polecenia SQL</span><span class="sxs-lookup"><span data-stu-id="eb471-122">Direct SQL Commands</span></span>  

 <span data-ttu-id="eb471-123">Czasami można napotkać sytuacje, w których możliwość <xref:System.Data.Linq.DataContext> wykonywania zapytań lub przesyłania zmian jest niewystarczająca dla wyspecjalizowanego zadania, które chcesz wykonać.</span><span class="sxs-lookup"><span data-stu-id="eb471-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="eb471-124">W takich przypadkach można użyć <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> metody do wydawania poleceń SQL do bazy danych i przekonwertowania wyników zapytania na obiekty.</span><span class="sxs-lookup"><span data-stu-id="eb471-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="eb471-125">Załóżmy na przykład, że dane dla `Customer` klasy są rozłożone na dwie tabele (customer1 i Customer2).</span><span class="sxs-lookup"><span data-stu-id="eb471-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="eb471-126">Następujące zapytanie zwraca sekwencję `Customer` obiektów:</span><span class="sxs-lookup"><span data-stu-id="eb471-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="eb471-127">Tak długo, jak nazwy kolumn w wynikach tabelarycznych są zgodne z właściwościami kolumny klasy Entity, program [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tworzy obiekty z dowolnego zapytania SQL.</span><span class="sxs-lookup"><span data-stu-id="eb471-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="eb471-128">Parametry</span><span class="sxs-lookup"><span data-stu-id="eb471-128">Parameters</span></span>  

 <span data-ttu-id="eb471-129"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A>Metoda przyjmuje parametry.</span><span class="sxs-lookup"><span data-stu-id="eb471-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="eb471-130">Poniższy kod wykonuje zapytanie parametryczne:</span><span class="sxs-lookup"><span data-stu-id="eb471-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="eb471-131">Parametry są wyrażane w tekście zapytania przy użyciu tej samej notacji klamrowej używanej przez `Console.WriteLine()` i `String.Format()` .</span><span class="sxs-lookup"><span data-stu-id="eb471-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="eb471-132">`String.Format()` Pobiera ciąg zapytania, który jest udostępniany i zastępuje parametry klamrowe z wygenerowanymi nazwami parametrów, takimi jak `@p0` , `@p1` ..., `@p(n)` .</span><span class="sxs-lookup"><span data-stu-id="eb471-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb471-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eb471-133">See also</span></span>

- [<span data-ttu-id="eb471-134">Informacje uzupełniające</span><span class="sxs-lookup"><span data-stu-id="eb471-134">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="eb471-135">Instrukcje: Ponowne użycie połączenia między poleceniem ADO.NET a DataContext</span><span class="sxs-lookup"><span data-stu-id="eb471-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
