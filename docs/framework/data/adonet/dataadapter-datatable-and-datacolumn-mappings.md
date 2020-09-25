---
title: Element DataAdapter DataTable i mapowania elementu DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: b979431836b55b23ac9ba6ec4535f33765dce555
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177738"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="a4887-102">Element DataAdapter DataTable i mapowania elementu DataColumn</span><span class="sxs-lookup"><span data-stu-id="a4887-102">DataAdapter DataTable and DataColumn Mappings</span></span>

<span data-ttu-id="a4887-103">Element **DataAdapter** zawiera kolekcję zero lub więcej <xref:System.Data.Common.DataTableMapping> obiektów we właściwości **TableMappings** .</span><span class="sxs-lookup"><span data-stu-id="a4887-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="a4887-104">**DataTableMapping** zapewnia mapowanie wzorca między danymi zwracanymi z zapytania do źródła danych i <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="a4887-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a4887-105">Nazwę **DataTableMapping** można przesłać zamiast nazwy **DataTable** do metody **Fill** elementu **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="a4887-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="a4887-106">Poniższy przykład tworzy **DataTableMapping** o nazwie **AuthorsMapping** dla tabeli **autorów** .</span><span class="sxs-lookup"><span data-stu-id="a4887-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="a4887-107">**DataTableMapping** umożliwia używanie nazw kolumn w **elemencie DataTable** , które różnią się od tych w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="a4887-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="a4887-108">Element **DataAdapter** używa mapowania, aby dopasować kolumny po zaktualizowaniu tabeli.</span><span class="sxs-lookup"><span data-stu-id="a4887-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="a4887-109">Jeśli nie określisz nazwy **TableName** lub **DataTableMapping** podczas wywoływania metody **Fill** lub **Update** elementu **DataAdapter**, obiekt **DataAdapter** szuka **DataTableMapping** o nazwie "Table".</span><span class="sxs-lookup"><span data-stu-id="a4887-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="a4887-110">Jeśli **DataTableMapping** nie istnieje, **tabelaname tabeli** **DataTable** ma wartość "Table".</span><span class="sxs-lookup"><span data-stu-id="a4887-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="a4887-111">Można określić domyślny **DataTableMapping** , tworząc **DataTableMapping** o nazwie "Table".</span><span class="sxs-lookup"><span data-stu-id="a4887-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="a4887-112">Poniższy przykład kodu tworzy **DataTableMapping** (z <xref:System.Data.Common> przestrzeni nazw) i tworzy mapowanie domyślne dla określonego elementu **DataAdapter** przez nadanie jej nazwy "Table".</span><span class="sxs-lookup"><span data-stu-id="a4887-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="a4887-113">Następnie przykład mapuje kolumny z pierwszej tabeli w wyniku zapytania (tabela **Customers** bazy danych **Northwind** ) do zestawu większej liczby przyjaznych nazw użytkowników w tabeli **Klienci Northwind** w <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="a4887-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a4887-114">W przypadku kolumn, które nie są zamapowane, używana jest nazwa kolumny ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="a4887-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="a4887-115">W bardziej zaawansowanych sytuacjach możesz zdecydować, że chcesz, aby ten sam element **DataAdapter** obsługiwał ładowanie różnych tabel z różnymi mapowaniami.</span><span class="sxs-lookup"><span data-stu-id="a4887-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="a4887-116">W tym celu wystarczy dodać dodatkowe obiekty **DataTableMapping** .</span><span class="sxs-lookup"><span data-stu-id="a4887-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="a4887-117">Gdy metoda **Fill** jest przenoszona do wystąpienia **zestawu danych** i nazwy **DataTableMapping** , jeśli istnieje mapowanie o tej nazwie, jest ono używane; w przeciwnym razie zostanie użyta **tabela DataTable** o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="a4887-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="a4887-118">Poniższe przykłady umożliwiają utworzenie **DataTableMapping** z nazwą **klientów** i nazwą **elementu DataTable** **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="a4887-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="a4887-119">Następnie przykład mapuje wiersze zwracane przez instrukcję SELECT do **elementu DataTable** **BizTalkSchema** .</span><span class="sxs-lookup"><span data-stu-id="a4887-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="a4887-120">Jeśli nie podano nazwy kolumny źródłowej dla mapowania kolumn lub nie podano nazwy tabeli źródłowej dla mapowania tabeli, automatycznie generowane są domyślne nazwy.</span><span class="sxs-lookup"><span data-stu-id="a4887-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="a4887-121">Jeśli nie podano kolumny źródłowej dla mapowania kolumn, mapowanie kolumny otrzymuje przyrostową domyślną nazwę **SourceColumn** *N,* rozpoczynając od **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="a4887-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="a4887-122">Jeśli nie podano nazwy tabeli źródłowej dla mapowania tabeli, mapowanie tabeli uzyskuje przyrostową domyślną nazwę elementu **SourceName** *N*, rozpoczynając od **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="a4887-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4887-123">Zalecamy uniknięcie konwencji nazewnictwa elementu **SourceColumn** *N* na potrzeby mapowania kolumn lub elementu **sources** *n* dla mapowania tabeli, ponieważ dostarczona nazwa może powodować konflikt z istniejącą domyślną nazwą mapowania kolumn w **DataTableMappingCollection**. **ColumnMappingCollection**</span><span class="sxs-lookup"><span data-stu-id="a4887-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="a4887-124">Jeśli podana nazwa już istnieje, zostanie zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a4887-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="a4887-125">Obsługa wielu zestawów wyników</span><span class="sxs-lookup"><span data-stu-id="a4887-125">Handling Multiple Result Sets</span></span>  

 <span data-ttu-id="a4887-126">Jeśli **Właściwość SelectCommand** zwraca wiele tabel, **Funkcja Fill** automatycznie generuje nazwy tabel z przyrostowymi wartościami dla tabel w **zestawie danych**, rozpoczynając od określonej nazwy tabeli i kontynuuje w formularzu **TableName** *N*, rozpoczynając od **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="a4887-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="a4887-127">Mapowania tabeli można użyć, aby zamapować automatycznie wygenerowaną nazwę tabeli na nazwę, która ma być określona dla tabeli w **zestawie danych**.</span><span class="sxs-lookup"><span data-stu-id="a4887-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="a4887-128">Na przykład dla elementu **SelectCommand** , który zwraca dwie tabele, **klienci** i **zamówienia**, wydaj następujące wywołanie do **wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="a4887-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="a4887-129">W **zestawie danych**są tworzone dwie tabele: **Customers** i **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="a4887-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="a4887-130">Mapowania tabel można użyć, aby upewnić się, że druga tabela ma nazwę **Orders** zamiast **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="a4887-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="a4887-131">W tym celu należy zmapować tabelę źródłową **Customers1** do **kolejności**tabel **zestawu danych** , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="a4887-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="a4887-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a4887-132">See also</span></span>

- [<span data-ttu-id="a4887-133">Elementy DataAdapter i DataReader</span><span class="sxs-lookup"><span data-stu-id="a4887-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="a4887-134">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a4887-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="a4887-135">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a4887-135">ADO.NET Overview</span></span>](ado-net-overview.md)
