---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: b5f2dbb687348afac98247cb21bae831dea26bfe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183315"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="8a35e-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="8a35e-102">DbProviderFactories</span></span>

<span data-ttu-id="8a35e-103"><xref:System.Data.Common>Przestrzeń nazw zawiera klasy służące do tworzenia <xref:System.Data.Common.DbProviderFactory> wystąpień do pracy z określonymi źródłami danych.</span><span class="sxs-lookup"><span data-stu-id="8a35e-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="8a35e-104">Po utworzeniu <xref:System.Data.Common.DbProviderFactory> wystąpienia i przejściu do niego informacji o dostawcy danych `DbProviderFactory` można określić poprawny obiekt połączenia o jednoznacznie określonym typie, który ma zostać zwrócony na podstawie dostarczonych informacji.</span><span class="sxs-lookup"><span data-stu-id="8a35e-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="8a35e-105">Począwszy od .NET Framework w wersji 4, dostawcy danych, takie jak <xref:System.Data.Odbc> ,, <xref:System.Data.OleDb> <xref:System.Data.SqlClient> i <xref:System.Data.OracleClient> nie są już wymienione w pliku machine.config, ale Dostawcy niestandardowi nadal będą wyświetlani w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="8a35e-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a35e-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="8a35e-106">In This Section</span></span>  

 [<span data-ttu-id="8a35e-107">Omówienie modelu fabryki</span><span class="sxs-lookup"><span data-stu-id="8a35e-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="8a35e-108">Zawiera omówienie wzorca projektowego i interfejsu programowania.</span><span class="sxs-lookup"><span data-stu-id="8a35e-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="8a35e-109">Uzyskiwanie DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="8a35e-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="8a35e-110">Pokazuje, jak wyświetlić listę zainstalowanych dostawców danych i utworzyć <xref:System.Data.Common.DbConnection> z programu `DbProviderFactory` .</span><span class="sxs-lookup"><span data-stu-id="8a35e-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="8a35e-111">DbConnection, DbCommand i DbException</span><span class="sxs-lookup"><span data-stu-id="8a35e-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="8a35e-112">Pokazuje, jak utworzyć <xref:System.Data.Common.DbCommand> i i <xref:System.Data.Common.DbDataReader> jak obsługiwać błędy danych przy użyciu programu <xref:System.Data.Common.DbException> .</span><span class="sxs-lookup"><span data-stu-id="8a35e-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="8a35e-113">Modyfikowanie danych za pomocą obiektu DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a35e-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="8a35e-114">Pokazuje, w jaki sposób używać elementu <xref:System.Data.Common.DbCommandBuilder> with a, <xref:System.Data.Common.DbDataAdapter> Aby pobierać i modyfikować dane.</span><span class="sxs-lookup"><span data-stu-id="8a35e-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a35e-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8a35e-115">See also</span></span>

- [<span data-ttu-id="8a35e-116">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a35e-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="8a35e-117">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a35e-117">ADO.NET Overview</span></span>](ado-net-overview.md)
