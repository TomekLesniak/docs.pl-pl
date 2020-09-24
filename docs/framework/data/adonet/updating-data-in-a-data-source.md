---
title: Aktualizowanie danych w źródle danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 6b0234337c85ace0797d75b72560ccb55635daae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177270"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="4e7c0-102">Aktualizowanie danych w źródle danych</span><span class="sxs-lookup"><span data-stu-id="4e7c0-102">Updating Data in a Data Source</span></span>

<span data-ttu-id="4e7c0-103">Instrukcje SQL, które modyfikują dane (takie jak INSERT, UPDATE lub DELETE) nie zwracają wierszy.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="4e7c0-104">Podobnie wiele procedur składowanych wykonuje akcję, ale nie zwraca wierszy.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="4e7c0-105">Aby wykonać polecenia, które nie zwracają wierszy, Utwórz obiekt **polecenia** z odpowiednim poleceniem SQL i **połączeniem**, włącznie z wymaganymi **parametrami**.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="4e7c0-106">Wykonaj polecenie za pomocą metody **ExecuteNonQuery** obiektu **Command** .</span><span class="sxs-lookup"><span data-stu-id="4e7c0-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="4e7c0-107">Metoda **ExecuteNonQuery** zwraca liczbę całkowitą, która odpowiada liczbie wierszy objętych instrukcją lub procedury składowanej, która została wykonana.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="4e7c0-108">W przypadku wykonywania wielu instrukcji zwracana wartość jest sumą rekordów, których dotyczą wszystkie wykonane instrukcje.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e7c0-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="4e7c0-109">Example</span></span>  

 <span data-ttu-id="4e7c0-110">Poniższy przykład kodu wykonuje instrukcję INSERT, aby wstawić rekord do bazy danych przy użyciu **ExecuteNonQuery**.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="4e7c0-111">Poniższy przykład kodu wykonuje procedurę przechowywaną utworzoną przez przykładowy kod podczas [wykonywania operacji katalogu](performing-catalog-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4e7c0-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="4e7c0-112">Procedura składowana nie zwraca żadnych wierszy, więc metoda **ExecuteNonQuery** jest używana, ale procedura składowana otrzymuje parametr wejściowy i zwraca parametr wyjściowy oraz wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="4e7c0-113">Dla <xref:System.Data.OleDb.OleDbCommand> obiektu należy najpierw dodać parametr **ReturnValue** do kolekcji **Parameters** .</span><span class="sxs-lookup"><span data-stu-id="4e7c0-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e7c0-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4e7c0-114">See also</span></span>

- [<span data-ttu-id="4e7c0-115">Używanie poleceń do modyfikacji danych</span><span class="sxs-lookup"><span data-stu-id="4e7c0-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="4e7c0-116">Aktualizowanie źródeł danych za pomocą elementów DataAdapter</span><span class="sxs-lookup"><span data-stu-id="4e7c0-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="4e7c0-117">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="4e7c0-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4e7c0-118">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4e7c0-118">ADO.NET Overview</span></span>](ado-net-overview.md)
