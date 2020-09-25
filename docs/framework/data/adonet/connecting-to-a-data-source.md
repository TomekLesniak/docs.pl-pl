---
title: Nawiązywanie połączenia ze źródłem danych
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: b9e69b029ad37c583e51c219f87ff9d7d8e7315c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203777"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="b9c4d-102">Nawiązywanie połączenia ze źródłem danych w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9c4d-102">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="b9c4d-103">W programie ADO.NET do łączenia się z określonym źródłem danych jest używany obiekt **połączenia** , dostarczając wymagane informacje o uwierzytelnianiu w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="b9c4d-103">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="b9c4d-104">Używany obiekt **połączenia** zależy od typu źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b9c4d-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="b9c4d-105">Każdy dostawca danych .NET Framework dołączony do .NET Framework ma <xref:System.Data.Common.DbConnection> obiekt: Dostawca danych .NET Framework dla OLE DB zawiera obiekt, .NET Framework dostawca danych dla <xref:System.Data.OleDb.OleDbConnection> SQL Server zawiera obiekt <xref:System.Data.SqlClient.SqlConnection> , .NET Framework dostawca danych dla ODBC zawiera obiekt, a .NET Framework dostawca danych <xref:System.Data.Odbc.OdbcConnection> dla programu Oracle zawiera <xref:System.Data.OracleClient.OracleConnection> obiekt.</span><span class="sxs-lookup"><span data-stu-id="b9c4d-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9c4d-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b9c4d-106">In This Section</span></span>  

 <span data-ttu-id="b9c4d-107">[Nawiązywanie połączenia](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="b9c4d-107">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="b9c4d-108">Opisuje sposób użycia obiektu **połączenia** w celu nawiązania połączenia ze źródłem danych.</span><span class="sxs-lookup"><span data-stu-id="b9c4d-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="b9c4d-109">[Zdarzenia połączenia](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="b9c4d-109">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="b9c4d-110">Opisuje sposób użycia zdarzenia **InfoMessage** do pobierania komunikatów informacyjnych ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b9c4d-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c4d-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9c4d-111">See also</span></span>

- [<span data-ttu-id="b9c4d-112">Parametry połączenia</span><span class="sxs-lookup"><span data-stu-id="b9c4d-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="b9c4d-113">Pula połączeń</span><span class="sxs-lookup"><span data-stu-id="b9c4d-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="b9c4d-114">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="b9c4d-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="b9c4d-115">Elementy DataAdapter i DataReader</span><span class="sxs-lookup"><span data-stu-id="b9c4d-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="b9c4d-116">Transakcje i współbieżność</span><span class="sxs-lookup"><span data-stu-id="b9c4d-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="b9c4d-117">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9c4d-117">ADO.NET Overview</span></span>](ado-net-overview.md)
