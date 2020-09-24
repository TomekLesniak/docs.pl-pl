---
title: Modyfikowanie danych za pomocą procedur składowanych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150755"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="c2f0f-102">Modyfikowanie danych za pomocą procedur składowanych</span><span class="sxs-lookup"><span data-stu-id="c2f0f-102">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="c2f0f-103">Procedury składowane mogą akceptować dane jako parametry wejściowe i mogą zwracać dane jako parametry wyjściowe, zestawy wyników lub wartości zwracane.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="c2f0f-104">W poniższym przykładzie pokazano, jak ADO.NET wysyła i odbiera parametry wejściowe, parametry wyjściowe oraz wartości zwracane.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="c2f0f-105">Przykład wstawia nowy rekord do tabeli, w której kolumna klucza podstawowego jest kolumną tożsamości w bazie danych SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2f0f-106">Jeśli używasz SQL Server procedur składowanych do edytowania lub usuwania danych przy użyciu programu <xref:System.Data.SqlClient.SqlDataAdapter> , upewnij się, że w definicji procedury składowanej nie używasz opcji SET NOCOUNT on.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="c2f0f-107">Powoduje to, że liczba zwracanych wierszy jest równa zero, która `DataAdapter` interpretuje jako konflikt współbieżności.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="c2f0f-108">W takim przypadku <xref:System.Data.DBConcurrencyException> zostanie zgłoszone zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2f0f-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="c2f0f-109">Example</span></span>  

 <span data-ttu-id="c2f0f-110">Przykład używa następującej procedury składowanej, aby wstawić nową kategorię do tabeli kategorii **Northwind** **Categories** .</span><span class="sxs-lookup"><span data-stu-id="c2f0f-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="c2f0f-111">Procedura składowana przyjmuje wartość w kolumnie **CategoryName** jako parametr wejściowy i używa funkcji SCOPE_IDENTITY (), aby pobrać nową wartość pola tożsamości, **IDkategorii**i zwrócić go w parametrze wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="c2f0f-112">Instrukcja RETURN używa funkcji @, @ROWCOUNT Aby zwrócić liczbę wstawionych wierszy.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="c2f0f-113">Poniższy przykład kodu używa `InsertCategory` procedury składowanej pokazanej powyżej jako źródła dla <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> elementu <xref:System.Data.SqlClient.SqlDataAdapter> .</span><span class="sxs-lookup"><span data-stu-id="c2f0f-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="c2f0f-114">`@Identity`Parametr wyjściowy zostanie odzwierciedlony w <xref:System.Data.DataSet> po wstawieniu rekordu do bazy danych, gdy `Update` <xref:System.Data.SqlClient.SqlDataAdapter> wywoływana jest metoda obiektu.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="c2f0f-115">Kod pobiera również wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2f0f-116">Podczas używania <xref:System.Data.OleDb.OleDbDataAdapter> , należy określić parametry z <xref:System.Data.ParameterDirection> **ReturnValue** przed innymi parametrami.</span><span class="sxs-lookup"><span data-stu-id="c2f0f-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c2f0f-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c2f0f-117">See also</span></span>

- [<span data-ttu-id="c2f0f-118">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c2f0f-118">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c2f0f-119">Elementy DataAdapter i DataReader</span><span class="sxs-lookup"><span data-stu-id="c2f0f-119">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c2f0f-120">Wykonywanie polecenia</span><span class="sxs-lookup"><span data-stu-id="c2f0f-120">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="c2f0f-121">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c2f0f-121">ADO.NET Overview</span></span>](ado-net-overview.md)
