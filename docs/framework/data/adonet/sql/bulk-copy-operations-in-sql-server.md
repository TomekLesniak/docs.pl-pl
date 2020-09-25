---
title: Operacje kopiowania masowego w programie SQL Server
description: Dowiedz się, jak używać klasy SqlBulkCopy do pisania rozwiązań kodu zarządzanego, które zbiorczo kopiują duże pliki do tabel lub widoków w bazach danych SQL Server.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197434"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="a1607-103">Operacje kopiowania masowego w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1607-103">Bulk Copy Operations in SQL Server</span></span>

<span data-ttu-id="a1607-104">Microsoft SQL Server obejmuje popularne narzędzie wiersza polecenia o nazwie **BCP** , aby szybko skopiować duże pliki do tabel lub widoków w bazach danych SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1607-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="a1607-105"><xref:System.Data.SqlClient.SqlBulkCopy>Klasa umożliwia pisanie rozwiązań kodu zarządzanego, które zapewniają podobną funkcjonalność.</span><span class="sxs-lookup"><span data-stu-id="a1607-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="a1607-106">Istnieją inne sposoby ładowania danych do tabeli SQL Server (na przykład instrukcje INSERT), ale <xref:System.Data.SqlClient.SqlBulkCopy> oferują one znaczącą wydajność.</span><span class="sxs-lookup"><span data-stu-id="a1607-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="a1607-107"><xref:System.Data.SqlClient.SqlBulkCopy>Klasa może służyć do zapisywania danych tylko w tabelach SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1607-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="a1607-108">Ale źródło danych nie jest ograniczone do SQL Server; można użyć dowolnego źródła danych, o ile dane mogą zostać załadowane do <xref:System.Data.DataTable> wystąpienia lub odczytane za pomocą <xref:System.Data.IDataReader> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a1607-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="a1607-109">Korzystając z <xref:System.Data.SqlClient.SqlBulkCopy> klasy, można wykonać następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="a1607-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="a1607-110">Pojedyncza operacja kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="a1607-111">Wiele operacji kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="a1607-112">Operacja kopiowania zbiorczego w ramach transakcji</span><span class="sxs-lookup"><span data-stu-id="a1607-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1607-113">W przypadku używania .NET Framework w wersji 1,1 lub starszej (która nie obsługuje <xref:System.Data.SqlClient.SqlBulkCopy> klasy) można wykonać SQL Server instrukcji języka Transact-SQL **BULK INSERT** przy użyciu <xref:System.Data.SqlClient.SqlCommand> obiektu.</span><span class="sxs-lookup"><span data-stu-id="a1607-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1607-114">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="a1607-114">In This Section</span></span>  

 [<span data-ttu-id="a1607-115">Konfiguracja przykładu kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="a1607-116">Opisuje tabele używane w przykładowych kopiach zbiorczych i udostępnia skrypty SQL do tworzenia tabel w bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a1607-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="a1607-117">Pojedyncze operacje kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="a1607-118">Opisuje, jak wykonać pojedynczą zbiorczą kopię danych w wystąpieniu SQL Server przy użyciu <xref:System.Data.SqlClient.SqlBulkCopy> klasy i jak wykonać operację kopiowania zbiorczego za pomocą instrukcji języka Transact-SQL i <xref:System.Data.SqlClient.SqlCommand> klasy.</span><span class="sxs-lookup"><span data-stu-id="a1607-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="a1607-119">Wiele operacji kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="a1607-120">Opisuje sposób wykonywania wielu operacji zbiorczych kopiowania danych do wystąpienia SQL Server przy użyciu <xref:System.Data.SqlClient.SqlBulkCopy> klasy.</span><span class="sxs-lookup"><span data-stu-id="a1607-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="a1607-121">Transakcja i operacje kopiowania zbiorczego</span><span class="sxs-lookup"><span data-stu-id="a1607-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="a1607-122">Opisuje sposób wykonywania operacji kopiowania zbiorczego w ramach transakcji, w tym metody zatwierdzania lub wycofywania transakcji.</span><span class="sxs-lookup"><span data-stu-id="a1607-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1607-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a1607-123">See also</span></span>

- [<span data-ttu-id="a1607-124">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1607-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="a1607-125">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1607-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
