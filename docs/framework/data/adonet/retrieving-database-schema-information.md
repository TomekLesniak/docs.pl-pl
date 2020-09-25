---
title: Pobieranie informacji o schemacie bazy danych
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177361"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="3fe03-102">Pobieranie informacji o schemacie bazy danych</span><span class="sxs-lookup"><span data-stu-id="3fe03-102">Retrieving Database Schema Information</span></span>

<span data-ttu-id="3fe03-103">Uzyskiwanie informacji o schemacie z bazy danych jest realizowane przy użyciu procesu odnajdywania schematu.</span><span class="sxs-lookup"><span data-stu-id="3fe03-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="3fe03-104">Funkcja odnajdywania schematów umożliwia aplikacjom żądanie, że dostawcy zarządzani znajdą i zwracają informacje o schemacie bazy danych, znane także jako *metadane*, danej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="3fe03-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="3fe03-105">Różne elementy schematu bazy danych, takie jak tabele, kolumny i procedury składowane, są udostępniane za poorednictwem kolekcji schematów.</span><span class="sxs-lookup"><span data-stu-id="3fe03-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="3fe03-106">Każda kolekcja schematów zawiera różne informacje o schemacie specyficzne dla używanego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="3fe03-107">Każdy z .NET Framework dostawców zarządzanych implementuje metodę **GetSchema** w klasie **Connection** , a informacje o schemacie, które są zwracane z metody **GetSchema** , mają postać <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="3fe03-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="3fe03-108">Metoda **GetSchema** jest przeciążoną metodą, która zapewnia parametry opcjonalne do określania kolekcji schematów do zwrócenia i ograniczając ilość zwracanych informacji.</span><span class="sxs-lookup"><span data-stu-id="3fe03-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="3fe03-109">Dostawcy danych .NET Framework dla OLE DB, ODBC, Oracle i SqlClient zapewniają metodę **Getschemaing** , która zwraca element DataTable opisujący metadane kolumn elementu **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="3fe03-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="3fe03-110">Dostawca danych .NET Framework dla OLE DB udostępnia również informacje o schemacie przy użyciu <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> metody <xref:System.Data.OleDb.OleDbConnection> obiektu.</span><span class="sxs-lookup"><span data-stu-id="3fe03-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="3fe03-111">Jako argumenty **GetOleDbSchemaTable** przyjmuje, <xref:System.Data.OleDb.OleDbSchemaGuid> że identyfikuje informacje o schemacie do zwrócenia i tablicę ograniczeń dla tych zwracanych kolumn.</span><span class="sxs-lookup"><span data-stu-id="3fe03-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="3fe03-112">**GetOleDbSchemaTable** zwraca <xref:System.Data.DataTable> wypełniony z żądanymi informacjami o schemacie.</span><span class="sxs-lookup"><span data-stu-id="3fe03-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fe03-113">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="3fe03-113">In This Section</span></span>  

 [<span data-ttu-id="3fe03-114">GetSchema i kolekcje schematów</span><span class="sxs-lookup"><span data-stu-id="3fe03-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="3fe03-115">Opisuje metodę **GetSchema** i sposób jej użycia do pobierania i ograniczania informacji schematu z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="3fe03-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="3fe03-116">Ograniczenia schematu</span><span class="sxs-lookup"><span data-stu-id="3fe03-116">Schema Restrictions</span></span>  
 <span data-ttu-id="3fe03-117">Opisuje ograniczenia schematu, które mogą być używane z **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="3fe03-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="3fe03-118">Typowe kolekcje schematów</span><span class="sxs-lookup"><span data-stu-id="3fe03-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="3fe03-119">Opisuje wszystkie typowe kolekcje schematów obsługiwane przez wszystkich .NET Framework zarządzanych dostawców.</span><span class="sxs-lookup"><span data-stu-id="3fe03-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="3fe03-120">Kolekcje schematów programu SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fe03-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="3fe03-121">Opisuje kolekcję schematów obsługiwaną przez dostawcę .NET Framework dla SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fe03-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="3fe03-122">Kolekcje schematów Oracle</span><span class="sxs-lookup"><span data-stu-id="3fe03-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="3fe03-123">Opisuje kolekcję schematów obsługiwaną przez dostawcę .NET Framework dla firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="3fe03-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="3fe03-124">Kolekcje schematów ODBC</span><span class="sxs-lookup"><span data-stu-id="3fe03-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="3fe03-125">Opisuje kolekcje schematów dla sterowników ODBC.</span><span class="sxs-lookup"><span data-stu-id="3fe03-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="3fe03-126">Kolekcje schematów OLE DB</span><span class="sxs-lookup"><span data-stu-id="3fe03-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="3fe03-127">Opisuje kolekcje schematów dla dostawców OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3fe03-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3fe03-128">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="3fe03-128">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="3fe03-129">Opisuje metodę **GetSchema** <xref:System.Data.Common.DbConnection> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="3fe03-130">Opisuje metodę **GetSchema** <xref:System.Data.Odbc.OdbcConnection> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="3fe03-131">Opisuje metodę **GetSchema** <xref:System.Data.OleDb.OleDbConnection> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="3fe03-132">Opisuje metodę **GetSchema** <xref:System.Data.OracleClient.OracleConnection> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="3fe03-133">Opisuje metodę **GetSchema** <xref:System.Data.SqlClient.SqlConnection> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3fe03-134">Opisuje metodę **Getschemaing** <xref:System.Data.Common.DbDataReader> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3fe03-135">Opisuje metodę **Getschemaing** <xref:System.Data.Odbc.OdbcDataReader> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3fe03-136">Opisuje metodę **Getschemaing** <xref:System.Data.OleDb.OleDbDataReader> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3fe03-137">Opisuje metodę **Getschemaing** <xref:System.Data.OracleClient.OracleDataReader> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3fe03-138">Opisuje metodę **Getschemaing** <xref:System.Data.SqlClient.SqlDataReader> klasy.</span><span class="sxs-lookup"><span data-stu-id="3fe03-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe03-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3fe03-139">See also</span></span>

- [<span data-ttu-id="3fe03-140">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3fe03-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="3fe03-141">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3fe03-141">ADO.NET Overview</span></span>](ado-net-overview.md)
