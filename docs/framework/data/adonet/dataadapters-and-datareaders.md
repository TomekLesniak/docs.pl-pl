---
title: Elementy DataAdapter i DataReader
description: Dowiedz się więcej o ADO.NET elemencie DataReader, który pobiera dane z bazy danych i DataAdapter, która pobiera dane ze źródła danych i wypełnia zestaw danych.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 2584f8b382dd90f2f8b4554663dc545b9ccceb62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177608"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="e732a-103">Elementy DataAdapter i DataReader</span><span class="sxs-lookup"><span data-stu-id="e732a-103">DataAdapters and DataReaders</span></span>

<span data-ttu-id="e732a-104">Za pomocą elementu **DataReader** ADO.NET można pobrać strumień danych tylko do odczytu z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-104">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="e732a-105">Wyniki są zwracane w miarę wykonywania zapytania i są przechowywane w buforze sieciowym na kliencie do momentu zażądania ich przy użyciu metody **Read** elementu **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="e732a-105">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="e732a-106">Użycie elementu **DataReader** może zwiększyć wydajność aplikacji, pobierając dane natychmiast po ich udostępnieniu i (domyślnie) przechowując tylko jeden wiersz jednocześnie w pamięci, zmniejszając obciążenie systemu.</span><span class="sxs-lookup"><span data-stu-id="e732a-106">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="e732a-107">A służy <xref:System.Data.Common.DataAdapter> do pobierania danych ze źródła danych i wypełniania tabel w <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="e732a-107">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="e732a-108">`DataAdapter`Rozwiązuje również zmiany wprowadzone w `DataSet` odwrocie do źródła danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-108">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="e732a-109">`DataAdapter`Używa `Connection` obiektu dostawcy danych .NET Framework do nawiązywania połączenia ze źródłem danych i używa `Command` obiektów do pobierania danych ze i rozwiązywania zmian w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-109">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="e732a-110">Każdy dostawca danych .NET Framework dołączony do .NET Framework ma <xref:System.Data.Common.DbDataReader> obiekt a i <xref:System.Data.Common.DbDataAdapter> obiektu: dostawca danych .NET Framework dla OLE DB zawiera i obiekt, .NET Framework Dostawca danych dla SQL Server zawiera a i obiekt <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.OleDb.OleDbDataAdapter> <xref:System.Data.SqlClient.SqlDataReader> <xref:System.Data.SqlClient.SqlDataAdapter> , .NET Framework dostawca danych dla ODBC zawiera obiekt <xref:System.Data.Odbc.OdbcDataReader> i <xref:System.Data.Odbc.OdbcDataAdapter> , a .NET Framework dostawca danych dla programu Oracle zawiera <xref:System.Data.OracleClient.OracleDataReader> obiekt i <xref:System.Data.OracleClient.OracleDataAdapter> .</span><span class="sxs-lookup"><span data-stu-id="e732a-110">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e732a-111">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="e732a-111">In This Section</span></span>  

 [<span data-ttu-id="e732a-112">Pobieranie danych przy użyciu elementu DataReader</span><span class="sxs-lookup"><span data-stu-id="e732a-112">Retrieving Data Using a DataReader</span></span>](retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="e732a-113">Opisuje obiekt ADO.NET **DataReader** i sposób użycia go do zwrócenia strumienia wyników ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-113">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="e732a-114">Wypełnianie zestawu danych z elementu DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e732a-114">Populating a DataSet from a DataAdapter</span></span>](populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="e732a-115">Opisuje sposób wypełniania `DataSet` tabelami, kolumnami i wierszami przy użyciu `DataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="e732a-115">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e732a-116">Parametry elementu DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e732a-116">DataAdapter Parameters</span></span>](dataadapter-parameters.md)  
 <span data-ttu-id="e732a-117">Opisuje sposób używania parametrów z właściwościami polecenia, `DataAdapter` w tym sposób mapowania zawartości kolumny w `DataSet` parametr do parametru polecenia.</span><span class="sxs-lookup"><span data-stu-id="e732a-117">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="e732a-118">Dodawanie istniejących ograniczeń do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="e732a-118">Adding Existing Constraints to a DataSet</span></span>](adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="e732a-119">Opisuje sposób dodawania istniejących ograniczeń do `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e732a-119">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="e732a-120">Element DataAdapter DataTable i mapowania elementu DataColumn</span><span class="sxs-lookup"><span data-stu-id="e732a-120">DataAdapter DataTable and DataColumn Mappings</span></span>](dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="e732a-121">Opisuje sposób konfigurowania `DataTableMappings` i `ColumnMappings` dla programu `DataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="e732a-121">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e732a-122">Stronicowanie za pośrednictwem wyniku zapytania</span><span class="sxs-lookup"><span data-stu-id="e732a-122">Paging Through a Query Result</span></span>](paging-through-a-query-result.md)  
 <span data-ttu-id="e732a-123">Przedstawia przykład wyświetlania wyników zapytania jako stron danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-123">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="e732a-124">Aktualizowanie źródeł danych za pomocą elementów DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e732a-124">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="e732a-125">Opisuje, jak za pomocą programu `DataAdapter` rozpoznać zmiany z `DataSet` powrotem do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e732a-125">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="e732a-126">Obsługa zdarzeń elementu DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e732a-126">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)  
 <span data-ttu-id="e732a-127">Zawiera opis `DataAdapter` zdarzeń i sposobu ich używania.</span><span class="sxs-lookup"><span data-stu-id="e732a-127">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="e732a-128">Wykonywanie operacji wsadowych za pomocą elementów DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e732a-128">Performing Batch Operations Using DataAdapters</span></span>](performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="e732a-129">Opisuje zwiększenie wydajności aplikacji przez zredukowanie liczby rund do SQL Server podczas stosowania aktualizacji z programu `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e732a-129">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e732a-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e732a-130">See also</span></span>

- [<span data-ttu-id="e732a-131">Nawiązywanie połączenia ze źródłem danych</span><span class="sxs-lookup"><span data-stu-id="e732a-131">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="e732a-132">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="e732a-132">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="e732a-133">Transakcje i współbieżność</span><span class="sxs-lookup"><span data-stu-id="e732a-133">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="e732a-134">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="e732a-134">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="e732a-135">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e732a-135">ADO.NET Overview</span></span>](ado-net-overview.md)
