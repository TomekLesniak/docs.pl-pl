---
title: Ograniczenia schematu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c0a3cafef45341cd95fa0a4f65c818129e120e44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147827"
---
# <a name="schema-restrictions"></a><span data-ttu-id="2c266-102">Ograniczenia schematu</span><span class="sxs-lookup"><span data-stu-id="2c266-102">Schema Restrictions</span></span>

<span data-ttu-id="2c266-103">Drugim parametrem opcjonalnym metody **GetSchema** jest ograniczenia, które są używane do ograniczenia ilości zwracanych informacji o schemacie i są przesyłane do metody **GetSchema** jako tablica ciągów.</span><span class="sxs-lookup"><span data-stu-id="2c266-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="2c266-104">Pozycja w tablicy określa wartości, które można przekazać, i jest równoważne z numerem ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="2c266-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="2c266-105">Na przykład w poniższej tabeli opisano ograniczenia obsługiwane przez kolekcję schematów "tabele" przy użyciu Dostawca danych .NET Framework dla SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c266-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="2c266-106">Dodatkowe ograniczenia dotyczące kolekcji schematów SQL Server są wymienione na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="2c266-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="2c266-107">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-107">Restriction Name</span></span>|<span data-ttu-id="2c266-108">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-108">Parameter Name</span></span>|<span data-ttu-id="2c266-109">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-109">Restriction Default</span></span>|<span data-ttu-id="2c266-110">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-111">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-111">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-112">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-113">1</span><span class="sxs-lookup"><span data-stu-id="2c266-113">1</span></span>|  
|<span data-ttu-id="2c266-114">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-114">Owner</span></span>|@Owner|<span data-ttu-id="2c266-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-116">2</span><span class="sxs-lookup"><span data-stu-id="2c266-116">2</span></span>|  
|<span data-ttu-id="2c266-117">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-117">Table</span></span>|@Name|<span data-ttu-id="2c266-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-118">TABLE_NAME</span></span>|<span data-ttu-id="2c266-119">3</span><span class="sxs-lookup"><span data-stu-id="2c266-119">3</span></span>|  
|<span data-ttu-id="2c266-120">Tabletype</span><span class="sxs-lookup"><span data-stu-id="2c266-120">TableType</span></span>|@TableType|<span data-ttu-id="2c266-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2c266-121">TABLE_TYPE</span></span>|<span data-ttu-id="2c266-122">4</span><span class="sxs-lookup"><span data-stu-id="2c266-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="2c266-123">Określanie wartości ograniczeń</span><span class="sxs-lookup"><span data-stu-id="2c266-123">Specifying Restriction Values</span></span>  

 <span data-ttu-id="2c266-124">Aby użyć jednego z ograniczeń kolekcji schematów "tabele", po prostu Utwórz tablicę ciągów z czterema elementami, a następnie umieść wartość w elemencie, który jest zgodny z numerem ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="2c266-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="2c266-125">Na przykład aby ograniczyć tabele zwracane przez metodę **GetSchema** do tylko tych tabel w schemacie "Sales", należy ustawić drugi element tablicy na "Sales" przed przekazaniem go do metody **GetSchema** .</span><span class="sxs-lookup"><span data-stu-id="2c266-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c266-126">Kolekcje ograniczeń dla `SqlClient` i `OracleClient` mają dodatkową `ParameterName` kolumnę.</span><span class="sxs-lookup"><span data-stu-id="2c266-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="2c266-127">Domyślna kolumna ograniczenia nadal ma zgodność z poprzednimi wersjami, ale jest obecnie ignorowana.</span><span class="sxs-lookup"><span data-stu-id="2c266-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="2c266-128">Zapytania sparametryzowane zamiast zamiany ciągu powinny służyć do zminimalizowania ryzyka związanego z iniekcją kodu SQL podczas określania wartości ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="2c266-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c266-129">Liczba elementów w tablicy musi być mniejsza lub równa liczbie ograniczeń, które są obsługiwane dla określonej kolekcji schematów, w przeciwnym razie <xref:System.ArgumentException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="2c266-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="2c266-130">Może być mniejsza niż maksymalna liczba ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="2c266-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="2c266-131">W przypadku brakujących ograniczeń przyjmuje się, że wartość jest równa null (bez ograniczeń).</span><span class="sxs-lookup"><span data-stu-id="2c266-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="2c266-132">Można wysłać zapytanie do dostawcy zarządzanego .NET Framework, aby określić listę obsługiwanych ograniczeń, wywołując metodę **GetSchema** z nazwą kolekcji schematów ograniczeń, która jest "ograniczenia".</span><span class="sxs-lookup"><span data-stu-id="2c266-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="2c266-133">Spowoduje to zwrócenie <xref:System.Data.DataTable> listy nazw kolekcji, nazw ograniczeń, domyślnych wartości ograniczeń oraz numerów ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="2c266-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c266-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="2c266-134">Example</span></span>  

 <span data-ttu-id="2c266-135">W poniższych przykładach pokazano, jak użyć <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metody Dostawca danych .NET Framework dla <xref:System.Data.SqlClient.SqlConnection> klasy SQL Server, aby pobrać informacje o schemacie dotyczące wszystkich tabel zawartych w przykładowej bazie danych **AdventureWorks** i ograniczyć zwrócone informacje do tych tabel w schemacie "sprzedaż":</span><span class="sxs-lookup"><span data-stu-id="2c266-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="2c266-136">SQL Server ograniczenia schematu</span><span class="sxs-lookup"><span data-stu-id="2c266-136">SQL Server Schema Restrictions</span></span>  

 <span data-ttu-id="2c266-137">W poniższej tabeli wymieniono ograniczenia dotyczące SQL Serverych kolekcji schematów.</span><span class="sxs-lookup"><span data-stu-id="2c266-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="2c266-138">Użytkownicy</span><span class="sxs-lookup"><span data-stu-id="2c266-138">Users</span></span>  
  
|<span data-ttu-id="2c266-139">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-139">Restriction Name</span></span>|<span data-ttu-id="2c266-140">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-140">Parameter Name</span></span>|<span data-ttu-id="2c266-141">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-141">Restriction Default</span></span>|<span data-ttu-id="2c266-142">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="2c266-143">User_Name</span></span>|@Name|<span data-ttu-id="2c266-144">name</span><span class="sxs-lookup"><span data-stu-id="2c266-144">name</span></span>|<span data-ttu-id="2c266-145">1</span><span class="sxs-lookup"><span data-stu-id="2c266-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="2c266-146">Bazy danych</span><span class="sxs-lookup"><span data-stu-id="2c266-146">Databases</span></span>  
  
|<span data-ttu-id="2c266-147">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-147">Restriction Name</span></span>|<span data-ttu-id="2c266-148">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-148">Parameter Name</span></span>|<span data-ttu-id="2c266-149">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-149">Restriction Default</span></span>|<span data-ttu-id="2c266-150">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-151">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2c266-151">Name</span></span>|@Name|<span data-ttu-id="2c266-152">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2c266-152">Name</span></span>|<span data-ttu-id="2c266-153">1</span><span class="sxs-lookup"><span data-stu-id="2c266-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="2c266-154">Tabele</span><span class="sxs-lookup"><span data-stu-id="2c266-154">Tables</span></span>  
  
|<span data-ttu-id="2c266-155">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-155">Restriction Name</span></span>|<span data-ttu-id="2c266-156">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-156">Parameter Name</span></span>|<span data-ttu-id="2c266-157">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-157">Restriction Default</span></span>|<span data-ttu-id="2c266-158">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-159">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-159">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-160">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-161">1</span><span class="sxs-lookup"><span data-stu-id="2c266-161">1</span></span>|  
|<span data-ttu-id="2c266-162">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-162">Owner</span></span>|@Owner|<span data-ttu-id="2c266-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-164">2</span><span class="sxs-lookup"><span data-stu-id="2c266-164">2</span></span>|  
|<span data-ttu-id="2c266-165">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-165">Table</span></span>|@Name|<span data-ttu-id="2c266-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-166">TABLE_NAME</span></span>|<span data-ttu-id="2c266-167">3</span><span class="sxs-lookup"><span data-stu-id="2c266-167">3</span></span>|  
|<span data-ttu-id="2c266-168">Tabletype</span><span class="sxs-lookup"><span data-stu-id="2c266-168">TableType</span></span>|@TableType|<span data-ttu-id="2c266-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2c266-169">TABLE_TYPE</span></span>|<span data-ttu-id="2c266-170">4</span><span class="sxs-lookup"><span data-stu-id="2c266-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2c266-171">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2c266-171">Columns</span></span>  
  
|<span data-ttu-id="2c266-172">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-172">Restriction Name</span></span>|<span data-ttu-id="2c266-173">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-173">Parameter Name</span></span>|<span data-ttu-id="2c266-174">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-174">Restriction Default</span></span>|<span data-ttu-id="2c266-175">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-176">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-176">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-177">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-178">1</span><span class="sxs-lookup"><span data-stu-id="2c266-178">1</span></span>|  
|<span data-ttu-id="2c266-179">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-179">Owner</span></span>|@Owner|<span data-ttu-id="2c266-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-181">2</span><span class="sxs-lookup"><span data-stu-id="2c266-181">2</span></span>|  
|<span data-ttu-id="2c266-182">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-182">Table</span></span>|@Table|<span data-ttu-id="2c266-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-183">TABLE_NAME</span></span>|<span data-ttu-id="2c266-184">3</span><span class="sxs-lookup"><span data-stu-id="2c266-184">3</span></span>|  
|<span data-ttu-id="2c266-185">Kolumna</span><span class="sxs-lookup"><span data-stu-id="2c266-185">Column</span></span>|@Column|<span data-ttu-id="2c266-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-186">COLUMN_NAME</span></span>|<span data-ttu-id="2c266-187">4</span><span class="sxs-lookup"><span data-stu-id="2c266-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="2c266-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="2c266-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="2c266-189">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-189">Restriction Name</span></span>|<span data-ttu-id="2c266-190">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-190">Parameter Name</span></span>|<span data-ttu-id="2c266-191">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-191">Restriction Default</span></span>|<span data-ttu-id="2c266-192">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-193">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-193">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-194">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-195">1</span><span class="sxs-lookup"><span data-stu-id="2c266-195">1</span></span>|  
|<span data-ttu-id="2c266-196">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-196">Owner</span></span>|@Owner|<span data-ttu-id="2c266-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-198">2</span><span class="sxs-lookup"><span data-stu-id="2c266-198">2</span></span>|  
|<span data-ttu-id="2c266-199">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-199">Table</span></span>|@Table|<span data-ttu-id="2c266-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-200">TABLE_NAME</span></span>|<span data-ttu-id="2c266-201">3</span><span class="sxs-lookup"><span data-stu-id="2c266-201">3</span></span>|  
|<span data-ttu-id="2c266-202">Kolumna</span><span class="sxs-lookup"><span data-stu-id="2c266-202">Column</span></span>|@Column|<span data-ttu-id="2c266-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-203">COLUMN_NAME</span></span>|<span data-ttu-id="2c266-204">4</span><span class="sxs-lookup"><span data-stu-id="2c266-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2c266-205">Widoki</span><span class="sxs-lookup"><span data-stu-id="2c266-205">Views</span></span>  
  
|<span data-ttu-id="2c266-206">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-206">Restriction Name</span></span>|<span data-ttu-id="2c266-207">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-207">Parameter Name</span></span>|<span data-ttu-id="2c266-208">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-208">Restriction Default</span></span>|<span data-ttu-id="2c266-209">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-210">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-210">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-211">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-212">1</span><span class="sxs-lookup"><span data-stu-id="2c266-212">1</span></span>|  
|<span data-ttu-id="2c266-213">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-213">Owner</span></span>|@Owner|<span data-ttu-id="2c266-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-215">2</span><span class="sxs-lookup"><span data-stu-id="2c266-215">2</span></span>|  
|<span data-ttu-id="2c266-216">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-216">Table</span></span>|@Table|<span data-ttu-id="2c266-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-217">TABLE_NAME</span></span>|<span data-ttu-id="2c266-218">3</span><span class="sxs-lookup"><span data-stu-id="2c266-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="2c266-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="2c266-219">ViewColumns</span></span>  
  
|<span data-ttu-id="2c266-220">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-220">Restriction Name</span></span>|<span data-ttu-id="2c266-221">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-221">Parameter Name</span></span>|<span data-ttu-id="2c266-222">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-222">Restriction Default</span></span>|<span data-ttu-id="2c266-223">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-224">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-224">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-225">VIEW_CATALOG</span></span>|<span data-ttu-id="2c266-226">1</span><span class="sxs-lookup"><span data-stu-id="2c266-226">1</span></span>|  
|<span data-ttu-id="2c266-227">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-227">Owner</span></span>|@Owner|<span data-ttu-id="2c266-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="2c266-229">2</span><span class="sxs-lookup"><span data-stu-id="2c266-229">2</span></span>|  
|<span data-ttu-id="2c266-230">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-230">Table</span></span>|@Table|<span data-ttu-id="2c266-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-231">VIEW_NAME</span></span>|<span data-ttu-id="2c266-232">3</span><span class="sxs-lookup"><span data-stu-id="2c266-232">3</span></span>|  
|<span data-ttu-id="2c266-233">Kolumna</span><span class="sxs-lookup"><span data-stu-id="2c266-233">Column</span></span>|@Column|<span data-ttu-id="2c266-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-234">COLUMN_NAME</span></span>|<span data-ttu-id="2c266-235">4</span><span class="sxs-lookup"><span data-stu-id="2c266-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="2c266-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2c266-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="2c266-237">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-237">Restriction Name</span></span>|<span data-ttu-id="2c266-238">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-238">Parameter Name</span></span>|<span data-ttu-id="2c266-239">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-239">Restriction Default</span></span>|<span data-ttu-id="2c266-240">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-241">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-241">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="2c266-243">1</span><span class="sxs-lookup"><span data-stu-id="2c266-243">1</span></span>|  
|<span data-ttu-id="2c266-244">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-244">Owner</span></span>|@Owner|<span data-ttu-id="2c266-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="2c266-246">2</span><span class="sxs-lookup"><span data-stu-id="2c266-246">2</span></span>|  
|<span data-ttu-id="2c266-247">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2c266-247">Name</span></span>|@Name|<span data-ttu-id="2c266-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="2c266-249">3</span><span class="sxs-lookup"><span data-stu-id="2c266-249">3</span></span>|  
|<span data-ttu-id="2c266-250">Parametr</span><span class="sxs-lookup"><span data-stu-id="2c266-250">Parameter</span></span>|@Parameter|<span data-ttu-id="2c266-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-251">PARAMETER_NAME</span></span>|<span data-ttu-id="2c266-252">4</span><span class="sxs-lookup"><span data-stu-id="2c266-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2c266-253">Procedury</span><span class="sxs-lookup"><span data-stu-id="2c266-253">Procedures</span></span>  
  
|<span data-ttu-id="2c266-254">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-254">Restriction Name</span></span>|<span data-ttu-id="2c266-255">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-255">Parameter Name</span></span>|<span data-ttu-id="2c266-256">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-256">Restriction Default</span></span>|<span data-ttu-id="2c266-257">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-258">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-258">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="2c266-260">1</span><span class="sxs-lookup"><span data-stu-id="2c266-260">1</span></span>|  
|<span data-ttu-id="2c266-261">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-261">Owner</span></span>|@Owner|<span data-ttu-id="2c266-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="2c266-263">2</span><span class="sxs-lookup"><span data-stu-id="2c266-263">2</span></span>|  
|<span data-ttu-id="2c266-264">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2c266-264">Name</span></span>|@Name|<span data-ttu-id="2c266-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="2c266-266">3</span><span class="sxs-lookup"><span data-stu-id="2c266-266">3</span></span>|  
|<span data-ttu-id="2c266-267">Typ</span><span class="sxs-lookup"><span data-stu-id="2c266-267">Type</span></span>|@Type|<span data-ttu-id="2c266-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2c266-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="2c266-269">4</span><span class="sxs-lookup"><span data-stu-id="2c266-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="2c266-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="2c266-270">IndexColumns</span></span>  
  
|<span data-ttu-id="2c266-271">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-271">Restriction Name</span></span>|<span data-ttu-id="2c266-272">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-272">Parameter Name</span></span>|<span data-ttu-id="2c266-273">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-273">Restriction Default</span></span>|<span data-ttu-id="2c266-274">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-275">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-275">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-276">db_name ()</span><span class="sxs-lookup"><span data-stu-id="2c266-276">db_name()</span></span>|<span data-ttu-id="2c266-277">1</span><span class="sxs-lookup"><span data-stu-id="2c266-277">1</span></span>|  
|<span data-ttu-id="2c266-278">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-278">Owner</span></span>|@Owner|<span data-ttu-id="2c266-279">user_name ()</span><span class="sxs-lookup"><span data-stu-id="2c266-279">user_name()</span></span>|<span data-ttu-id="2c266-280">2</span><span class="sxs-lookup"><span data-stu-id="2c266-280">2</span></span>|  
|<span data-ttu-id="2c266-281">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-281">Table</span></span>|@Table|<span data-ttu-id="2c266-282">o.name</span><span class="sxs-lookup"><span data-stu-id="2c266-282">o.name</span></span>|<span data-ttu-id="2c266-283">3</span><span class="sxs-lookup"><span data-stu-id="2c266-283">3</span></span>|  
|<span data-ttu-id="2c266-284">Element ConstraintName</span><span class="sxs-lookup"><span data-stu-id="2c266-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="2c266-285">x.name</span><span class="sxs-lookup"><span data-stu-id="2c266-285">x.name</span></span>|<span data-ttu-id="2c266-286">4</span><span class="sxs-lookup"><span data-stu-id="2c266-286">4</span></span>|  
|<span data-ttu-id="2c266-287">Kolumna</span><span class="sxs-lookup"><span data-stu-id="2c266-287">Column</span></span>|@Column|<span data-ttu-id="2c266-288">c.name</span><span class="sxs-lookup"><span data-stu-id="2c266-288">c.name</span></span>|<span data-ttu-id="2c266-289">5</span><span class="sxs-lookup"><span data-stu-id="2c266-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2c266-290">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2c266-290">Indexes</span></span>  
  
|<span data-ttu-id="2c266-291">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-291">Restriction Name</span></span>|<span data-ttu-id="2c266-292">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-292">Parameter Name</span></span>|<span data-ttu-id="2c266-293">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-293">Restriction Default</span></span>|<span data-ttu-id="2c266-294">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-295">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-295">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-296">db_name ()</span><span class="sxs-lookup"><span data-stu-id="2c266-296">db_name()</span></span>|<span data-ttu-id="2c266-297">1</span><span class="sxs-lookup"><span data-stu-id="2c266-297">1</span></span>|  
|<span data-ttu-id="2c266-298">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-298">Owner</span></span>|@Owner|<span data-ttu-id="2c266-299">user_name ()</span><span class="sxs-lookup"><span data-stu-id="2c266-299">user_name()</span></span>|<span data-ttu-id="2c266-300">2</span><span class="sxs-lookup"><span data-stu-id="2c266-300">2</span></span>|  
|<span data-ttu-id="2c266-301">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-301">Table</span></span>|@Table|<span data-ttu-id="2c266-302">o.name</span><span class="sxs-lookup"><span data-stu-id="2c266-302">o.name</span></span>|<span data-ttu-id="2c266-303">3</span><span class="sxs-lookup"><span data-stu-id="2c266-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="2c266-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="2c266-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="2c266-305">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-305">Restriction Name</span></span>|<span data-ttu-id="2c266-306">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-306">Parameter Name</span></span>|<span data-ttu-id="2c266-307">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-307">Restriction Default</span></span>|<span data-ttu-id="2c266-308">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="2c266-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="2c266-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="2c266-310">assemblies.name</span></span>|<span data-ttu-id="2c266-311">1</span><span class="sxs-lookup"><span data-stu-id="2c266-311">1</span></span>|  
|<span data-ttu-id="2c266-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="2c266-312">udt_name</span></span>|@UDTName|<span data-ttu-id="2c266-313">typy. assembly_class</span><span class="sxs-lookup"><span data-stu-id="2c266-313">types.assembly_class</span></span>|<span data-ttu-id="2c266-314">2</span><span class="sxs-lookup"><span data-stu-id="2c266-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="2c266-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="2c266-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="2c266-316">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-316">Restriction Name</span></span>|<span data-ttu-id="2c266-317">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-317">Parameter Name</span></span>|<span data-ttu-id="2c266-318">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-318">Restriction Default</span></span>|<span data-ttu-id="2c266-319">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-320">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-320">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="2c266-322">1</span><span class="sxs-lookup"><span data-stu-id="2c266-322">1</span></span>|  
|<span data-ttu-id="2c266-323">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-323">Owner</span></span>|@Owner|<span data-ttu-id="2c266-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="2c266-325">2</span><span class="sxs-lookup"><span data-stu-id="2c266-325">2</span></span>|  
|<span data-ttu-id="2c266-326">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-326">Table</span></span>|@Table|<span data-ttu-id="2c266-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-327">TABLE_NAME</span></span>|<span data-ttu-id="2c266-328">3</span><span class="sxs-lookup"><span data-stu-id="2c266-328">3</span></span>|  
|<span data-ttu-id="2c266-329">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2c266-329">Name</span></span>|@Name|<span data-ttu-id="2c266-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="2c266-331">4</span><span class="sxs-lookup"><span data-stu-id="2c266-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="2c266-332">Ograniczenia schematu SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="2c266-332">SQL Server 2008 Schema Restrictions</span></span>  

 <span data-ttu-id="2c266-333">W poniższej tabeli wymieniono ograniczenia dotyczące kolekcji schematów SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2c266-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="2c266-334">Te ograniczenia są prawidłowe od wersji 3,5 SP1 .NET Framework i SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2c266-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="2c266-335">Nie są one obsługiwane we wcześniejszych wersjach .NET Framework i SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c266-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="2c266-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="2c266-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="2c266-337">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-337">Restriction Name</span></span>|<span data-ttu-id="2c266-338">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-338">Parameter Name</span></span>|<span data-ttu-id="2c266-339">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-339">Restriction Default</span></span>|<span data-ttu-id="2c266-340">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-341">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-341">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-342">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-343">1</span><span class="sxs-lookup"><span data-stu-id="2c266-343">1</span></span>|  
|<span data-ttu-id="2c266-344">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-344">Owner</span></span>|@Owner|<span data-ttu-id="2c266-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-346">2</span><span class="sxs-lookup"><span data-stu-id="2c266-346">2</span></span>|  
|<span data-ttu-id="2c266-347">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-347">Table</span></span>|@Table|<span data-ttu-id="2c266-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-348">TABLE_NAME</span></span>|<span data-ttu-id="2c266-349">3</span><span class="sxs-lookup"><span data-stu-id="2c266-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="2c266-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="2c266-350">AllColumns</span></span>  
  
|<span data-ttu-id="2c266-351">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-351">Restriction Name</span></span>|<span data-ttu-id="2c266-352">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="2c266-352">Parameter Name</span></span>|<span data-ttu-id="2c266-353">Domyślne ograniczenie</span><span class="sxs-lookup"><span data-stu-id="2c266-353">Restriction Default</span></span>|<span data-ttu-id="2c266-354">Numer ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2c266-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="2c266-355">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2c266-355">Catalog</span></span>|@Catalog|<span data-ttu-id="2c266-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2c266-356">TABLE_CATALOG</span></span>|<span data-ttu-id="2c266-357">1</span><span class="sxs-lookup"><span data-stu-id="2c266-357">1</span></span>|  
|<span data-ttu-id="2c266-358">Właściciel</span><span class="sxs-lookup"><span data-stu-id="2c266-358">Owner</span></span>|@Owner|<span data-ttu-id="2c266-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2c266-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="2c266-360">2</span><span class="sxs-lookup"><span data-stu-id="2c266-360">2</span></span>|  
|<span data-ttu-id="2c266-361">tabela</span><span class="sxs-lookup"><span data-stu-id="2c266-361">Table</span></span>|@Table|<span data-ttu-id="2c266-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-362">TABLE_NAME</span></span>|<span data-ttu-id="2c266-363">3</span><span class="sxs-lookup"><span data-stu-id="2c266-363">3</span></span>|  
|<span data-ttu-id="2c266-364">Kolumna</span><span class="sxs-lookup"><span data-stu-id="2c266-364">Column</span></span>|@Column|<span data-ttu-id="2c266-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2c266-365">COLUMN_NAME</span></span>|<span data-ttu-id="2c266-366">4</span><span class="sxs-lookup"><span data-stu-id="2c266-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c266-367">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2c266-367">See also</span></span>

- [<span data-ttu-id="2c266-368">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c266-368">ADO.NET Overview</span></span>](ado-net-overview.md)
