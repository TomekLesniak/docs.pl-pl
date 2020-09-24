---
title: Uzyskiwanie pojedynczej wartości z bazy danych
description: Dowiedz się, jak zwrócić pojedynczą wartość w ADO.NET. Ten przykładowy kod zwraca wartość kolumny tożsamości dla wstawionego rekordu.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150729"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="33141-104">Uzyskiwanie pojedynczej wartości z bazy danych</span><span class="sxs-lookup"><span data-stu-id="33141-104">Obtaining a Single Value from a Database</span></span>

<span data-ttu-id="33141-105">Może być konieczne zwrócenie informacji o bazie danych, która jest po prostu pojedynczą wartością, a nie w formie tabeli lub strumienia danych.</span><span class="sxs-lookup"><span data-stu-id="33141-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="33141-106">Na przykład możesz chcieć zwrócić wynik funkcji agregującej, takiej jak COUNT ( \* ), sum (Price) lub AVG (ilość).</span><span class="sxs-lookup"><span data-stu-id="33141-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="33141-107">Obiekt **Command** oferuje możliwość zwracania pojedynczych wartości przy użyciu metody **ExecuteScalar** .</span><span class="sxs-lookup"><span data-stu-id="33141-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="33141-108">Metoda **ExecuteScalar** zwraca, jako wartość skalarną, wartość pierwszej kolumny pierwszego wiersza w zestawie wyników.</span><span class="sxs-lookup"><span data-stu-id="33141-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="33141-109">Poniższy przykład kodu wstawia nową wartość w bazie danych przy użyciu <xref:System.Data.SqlClient.SqlCommand> .</span><span class="sxs-lookup"><span data-stu-id="33141-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="33141-110"><xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>Metoda jest używana do zwracania wartości kolumny Identity dla wstawionego rekordu.</span><span class="sxs-lookup"><span data-stu-id="33141-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="33141-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="33141-111">See also</span></span>

- [<span data-ttu-id="33141-112">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="33141-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="33141-113">Wykonywanie polecenia</span><span class="sxs-lookup"><span data-stu-id="33141-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="33141-114">DbConnection, DbCommand i DbException</span><span class="sxs-lookup"><span data-stu-id="33141-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="33141-115">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="33141-115">ADO.NET Overview</span></span>](ado-net-overview.md)
