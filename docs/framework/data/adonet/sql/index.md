---
title: SQL Server i ADO.NET
description: Dowiedz się więcej na temat funkcji i zachowań Dostawca danych .NET Framework dla SQL Server, które hermetyzują protokoły specyficzne dla bazy danych.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: a517bccd9b60d00f6c6c636c9164d63fb5966de3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197394"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="6aa48-103">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-103">SQL Server and ADO.NET</span></span>

<span data-ttu-id="6aa48-104">W tej sekcji opisano funkcje i zachowania, które są specyficzne dla Dostawca danych .NET Framework dla SQL Server ( <xref:System.Data.SqlClient> ).</span><span class="sxs-lookup"><span data-stu-id="6aa48-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="6aa48-105"><xref:System.Data.SqlClient> zapewnia dostęp do wersji SQL Server, które hermetyzują protokoły specyficzne dla bazy danych.</span><span class="sxs-lookup"><span data-stu-id="6aa48-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="6aa48-106">Funkcja dostawcy danych została zaprojektowana tak, aby była podobna do .NET Framework dostawców danych dla OLE DB, ODBC i Oracle.</span><span class="sxs-lookup"><span data-stu-id="6aa48-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="6aa48-107"><xref:System.Data.SqlClient> zawiera Analizator strumienia danych tabelarycznych (TDS) do bezpośredniego komunikowania się z SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aa48-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6aa48-108">Aby można było użyć Dostawca danych .NET Framework na potrzeby SQL Server, aplikacja musi odwoływać się do <xref:System.Data.SqlClient> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="6aa48-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6aa48-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="6aa48-109">In This Section</span></span>  

 [<span data-ttu-id="6aa48-110">Zabezpieczenia serwera SQL</span><span class="sxs-lookup"><span data-stu-id="6aa48-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="6aa48-111">Zawiera omówienie funkcji zabezpieczeń SQL Server i scenariuszy aplikacji do tworzenia bezpiecznych aplikacji ADO.NET, które są przeznaczone SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aa48-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="6aa48-112">Typy danych programu SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="6aa48-113">Opisuje sposób pracy z SQL Server typami danych i sposobami ich współpracy z .NET Framework typami danych.</span><span class="sxs-lookup"><span data-stu-id="6aa48-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="6aa48-114">Dane binarne i dużej wartości w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="6aa48-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="6aa48-115">Opisuje sposób pracy z danymi dużej wartości w SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aa48-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="6aa48-116">Operacje danych serwera SQL w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="6aa48-117">Opisuje sposób pracy z danymi w SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aa48-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="6aa48-118">Zawiera sekcje dotyczące operacji kopiowania zbiorczego, operacji MARS, asynchronicznych i parametrów z wartościami przechowywanymi w tabeli.</span><span class="sxs-lookup"><span data-stu-id="6aa48-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="6aa48-119">Funkcje Serwera SQL i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="6aa48-120">Opisuje funkcje SQL Server, które są przydatne w przypadku deweloperów aplikacji ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="6aa48-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="6aa48-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6aa48-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="6aa48-122">Zawiera opis podstawowych bloków konstrukcyjnych, procesów i technik wymaganych do tworzenia aplikacji LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="6aa48-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="6aa48-123">Aby uzyskać pełną dokumentację aparatu bazy danych SQL Server, zobacz SQL Server Books Online dla używanej wersji programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aa48-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="6aa48-124">Książka SQL Server online</span><span class="sxs-lookup"><span data-stu-id="6aa48-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="6aa48-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6aa48-125">See also</span></span>

- [<span data-ttu-id="6aa48-126">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="6aa48-127">Mapowanie typu danych w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="6aa48-128">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="6aa48-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="6aa48-129">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="6aa48-130">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6aa48-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
