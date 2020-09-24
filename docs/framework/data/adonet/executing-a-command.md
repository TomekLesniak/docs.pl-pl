---
title: Wykonywanie polecenia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: d7d290c1c149f9eab2449c25e8d32f2568eb0277
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156462"
---
# <a name="executing-a-command"></a><span data-ttu-id="3194c-102">Wykonywanie polecenia</span><span class="sxs-lookup"><span data-stu-id="3194c-102">Executing a Command</span></span>

<span data-ttu-id="3194c-103">Każdy dostawca danych .NET Framework dołączony do .NET Framework ma własny obiekt polecenia, który dziedziczy z <xref:System.Data.Common.DbCommand> .</span><span class="sxs-lookup"><span data-stu-id="3194c-103">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="3194c-104">Dostawca danych .NET Framework dla OLE DB zawiera obiekt <xref:System.Data.OleDb.OleDbCommand> , .NET Framework dostawca danych dla SQL Server zawiera obiekt <xref:System.Data.SqlClient.SqlCommand> , .NET Framework dostawca danych dla ODBC zawiera obiekt <xref:System.Data.Odbc.OdbcCommand> , a .NET Framework dostawca danych dla programu Oracle zawiera <xref:System.Data.OracleClient.OracleCommand> obiekt.</span><span class="sxs-lookup"><span data-stu-id="3194c-104">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="3194c-105">Każdy z tych obiektów uwidacznia metody wykonywania poleceń na podstawie typu polecenia i żądanej wartości zwracanej, zgodnie z opisem w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="3194c-105">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="3194c-106">Polecenie</span><span class="sxs-lookup"><span data-stu-id="3194c-106">Command</span></span>|<span data-ttu-id="3194c-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3194c-107">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="3194c-108">Zwraca `DataReader` obiektu.</span><span class="sxs-lookup"><span data-stu-id="3194c-108">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="3194c-109">Zwraca pojedynczą wartość skalarną.</span><span class="sxs-lookup"><span data-stu-id="3194c-109">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="3194c-110">Wykonuje polecenie, które nie zwraca żadnych wierszy.</span><span class="sxs-lookup"><span data-stu-id="3194c-110">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="3194c-111">Zwraca wartość <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="3194c-111">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="3194c-112">Dostępne tylko dla `SqlCommand` obiektu.</span><span class="sxs-lookup"><span data-stu-id="3194c-112">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="3194c-113">Każdy obiekt polecenia o jednoznacznie określonym typie obsługuje również <xref:System.Data.CommandType> Wyliczenie, które określa sposób interpretacji ciągu polecenia, zgodnie z opisem w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="3194c-113">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="3194c-114">CommandType</span><span class="sxs-lookup"><span data-stu-id="3194c-114">CommandType</span></span>|<span data-ttu-id="3194c-115">Opis</span><span class="sxs-lookup"><span data-stu-id="3194c-115">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="3194c-116">Polecenie SQL definiujące instrukcje do wykonania w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="3194c-116">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="3194c-117">Nazwa procedury składowanej.</span><span class="sxs-lookup"><span data-stu-id="3194c-117">The name of the stored procedure.</span></span> <span data-ttu-id="3194c-118">Można użyć `Parameters` Właściwości polecenia, aby uzyskać dostęp do parametrów wejściowych i wyjściowych oraz zwracanych wartości, niezależnie od tego, która `Execute` Metoda jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="3194c-118">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="3194c-119">W przypadku używania `ExecuteReader` wartości zwracane i parametry wyjściowe nie będą dostępne do momentu `DataReader` zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="3194c-119">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="3194c-120">Nazwa tabeli.</span><span class="sxs-lookup"><span data-stu-id="3194c-120">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3194c-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="3194c-121">Example</span></span>  

 <span data-ttu-id="3194c-122">Poniższy przykład kodu demonstruje sposób tworzenia <xref:System.Data.SqlClient.SqlCommand> obiektu do wykonania procedury składowanej przez ustawienie jej właściwości.</span><span class="sxs-lookup"><span data-stu-id="3194c-122">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="3194c-123"><xref:System.Data.SqlClient.SqlParameter>Obiekt jest używany do określenia parametru wejściowego procedury składowanej.</span><span class="sxs-lookup"><span data-stu-id="3194c-123">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="3194c-124">Polecenie jest wykonywane przy użyciu <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> metody, a dane wyjściowe z programu <xref:System.Data.SqlClient.SqlDataReader> są wyświetlane w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="3194c-124">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="3194c-125">Rozwiązywanie problemów z poleceniami</span><span class="sxs-lookup"><span data-stu-id="3194c-125">Troubleshooting Commands</span></span>  

 <span data-ttu-id="3194c-126">.NET Framework Dostawca danych do SQL Server dodaje liczniki wydajności, aby umożliwić wykrywanie sporadycznych problemów związanych z operacjami zakończonymi niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="3194c-126">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="3194c-127">Aby uzyskać więcej informacji, zobacz [liczniki wydajności](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="3194c-127">For more information see [Performance Counters](performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3194c-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3194c-128">See also</span></span>

- [<span data-ttu-id="3194c-129">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="3194c-129">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="3194c-130">Elementy DataAdapter i DataReader</span><span class="sxs-lookup"><span data-stu-id="3194c-130">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="3194c-131">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3194c-131">ADO.NET Overview</span></span>](ado-net-overview.md)
