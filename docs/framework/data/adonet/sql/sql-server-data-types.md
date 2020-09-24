---
title: Typy danych programu SQL Server i ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155461"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="c51cc-102">Typy danych programu SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c51cc-102">SQL Server Data Types and ADO.NET</span></span>

<span data-ttu-id="c51cc-103">SQL Server i .NET Framework są oparte na różnych systemach typu, co może spowodować utratę danych.</span><span class="sxs-lookup"><span data-stu-id="c51cc-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="c51cc-104">Aby zachować integralność danych, Dostawca danych .NET Framework dla SQL Server ( <xref:System.Data.SqlClient> ) zapewnia metody dostępu typu Type do pracy z danymi SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c51cc-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="c51cc-105">Możesz użyć wyliczeń w <xref:System.Data.SqlDbType> klasach, aby określić <xref:System.Data.SqlClient.SqlParameter> typy danych.</span><span class="sxs-lookup"><span data-stu-id="c51cc-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="c51cc-106">Aby uzyskać więcej informacji i tabelę opisującą mapowanie typu danych między SQL Server i .NET Framework typy danych, zobacz [SQL Server mapowania typów danych](../sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="c51cc-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="c51cc-107">SQL Server 2008 wprowadza nowe typy danych, które są przeznaczone do zaspokajania potrzeb firmy, do pracy z danymi o dacie i godzinie, ze strukturą, częściową strukturą i bez struktury.</span><span class="sxs-lookup"><span data-stu-id="c51cc-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="c51cc-108">Są one udokumentowane w SQL Server 2008 książki online.</span><span class="sxs-lookup"><span data-stu-id="c51cc-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="c51cc-109">SQL Server typy danych, które są dostępne do użycia w aplikacji, zależą od używanej wersji programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c51cc-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="c51cc-110">Aby uzyskać więcej informacji, zobacz odpowiednią wersję dokumentacji SQL Server Books Online w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c51cc-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="c51cc-111">**Dokumentacja SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c51cc-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="c51cc-112">Typy danych (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c51cc-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="c51cc-113">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="c51cc-113">In This Section</span></span>  

 [<span data-ttu-id="c51cc-114">Właściwość SqlTypes i zestaw danych</span><span class="sxs-lookup"><span data-stu-id="c51cc-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="c51cc-115">Opisuje obsługę typów `SqlTypes` w programie `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="c51cc-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="c51cc-116">Obsługa wartości Null</span><span class="sxs-lookup"><span data-stu-id="c51cc-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="c51cc-117">Pokazuje, jak korzystać z wartości null i logiki z trzema wartościami.</span><span class="sxs-lookup"><span data-stu-id="c51cc-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="c51cc-118">Porównywanie identyfikatora GUID i wartości uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c51cc-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="c51cc-119">Demonstruje sposób pracy z identyfikatorami GUID i unikatowymi wartościami w SQL Server i .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c51cc-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="c51cc-120">Dane daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c51cc-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="c51cc-121">Opisuje sposób korzystania z nowych typów danych daty i godziny wprowadzonych w SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c51cc-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="c51cc-122">Duże UDT</span><span class="sxs-lookup"><span data-stu-id="c51cc-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="c51cc-123">Demonstruje sposób pobierania danych z UDTs dużej wartości wprowadzonych w SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c51cc-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="c51cc-124">Dane XML w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="c51cc-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="c51cc-125">Opisuje sposób pracy z danymi XML pobranymi z SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c51cc-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c51cc-126">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="c51cc-126">Reference</span></span>  

 <xref:System.Data.DataSet>  
 <span data-ttu-id="c51cc-127">Opisuje `DataSet` klasę i wszystkich jej członków.</span><span class="sxs-lookup"><span data-stu-id="c51cc-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="c51cc-128">Zawiera opis `SqlTypes` przestrzeni nazw i wszystkich jej elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="c51cc-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="c51cc-129">Opisuje `SqlDbType` Wyliczenie i wszystkie jego elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="c51cc-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="c51cc-130">Opisuje `DbType` Wyliczenie i wszystkie jego elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="c51cc-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51cc-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c51cc-131">See also</span></span>

- [<span data-ttu-id="c51cc-132">Mapowanie typu danych serwera SQL</span><span class="sxs-lookup"><span data-stu-id="c51cc-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="c51cc-133">Konfigurowanie parametrów i typów danych parametrów</span><span class="sxs-lookup"><span data-stu-id="c51cc-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="c51cc-134">Parametry o wartościach tabelowych</span><span class="sxs-lookup"><span data-stu-id="c51cc-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="c51cc-135">Dane binarne i dużej wartości w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="c51cc-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="c51cc-136">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c51cc-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
