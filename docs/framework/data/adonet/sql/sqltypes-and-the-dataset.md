---
title: Właściwość SqlTypes i zestaw danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147511"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="0c10f-102">Właściwość SqlTypes i zestaw danych</span><span class="sxs-lookup"><span data-stu-id="0c10f-102">SqlTypes and the DataSet</span></span>

<span data-ttu-id="0c10f-103">W systemie ADO.NET 2,0 wprowadzono rozszerzoną obsługę typów w `DataSet`  <xref:System.Data.SqlTypes> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0c10f-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="0c10f-104">Typy w programie <xref:System.Data.SqlTypes> zaprojektowano w celu zapewnienia typów danych z tą samą semantyką i dokładnością jako typami danych w bazie danych SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c10f-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="0c10f-105">Każdy typ danych w <xref:System.Data.SqlTypes> ma odpowiedni typ danych w SQL Server, z tą samą reprezentacją danych.</span><span class="sxs-lookup"><span data-stu-id="0c10f-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="0c10f-106">Użycie <xref:System.Data.SqlTypes> bezpośrednio w przystawce <xref:System.Data.DataSet> przydaje kilka korzyści podczas pracy z SQL Server typami danych.</span><span class="sxs-lookup"><span data-stu-id="0c10f-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="0c10f-107"><xref:System.Data.SqlTypes> obsługuje te same semantykę co SQL Server natywne typy danych.</span><span class="sxs-lookup"><span data-stu-id="0c10f-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="0c10f-108">Określanie jednej z <xref:System.Data.SqlTypes> w definicji a <xref:System.Data.DataColumn> eliminuje utratę dokładności, która może wystąpić podczas konwertowania dziesiętnych lub liczbowych typów danych na jeden z typów danych środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="0c10f-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c10f-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="0c10f-109">Example</span></span>  

 <span data-ttu-id="0c10f-110">Poniższy przykład tworzy <xref:System.Data.DataTable> obiekt, jawnie definiując <xref:System.Data.DataColumn> typy danych przy użyciu <xref:System.Data.SqlTypes> zamiast typów CLR.</span><span class="sxs-lookup"><span data-stu-id="0c10f-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="0c10f-111">Kod wypełnia dane z <xref:System.Data.DataTable> tabeli Sales. SalesOrderDetail w bazie danych AdventureWorks w SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c10f-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="0c10f-112">Dane wyjściowe wyświetlane w oknie konsoli programu pokazują typ danych każdej kolumny i wartości pobrane z SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c10f-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c10f-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c10f-113">See also</span></span>

- [<span data-ttu-id="0c10f-114">Mapowanie typu danych serwera SQL</span><span class="sxs-lookup"><span data-stu-id="0c10f-114">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="0c10f-115">Konfigurowanie parametrów i typów danych parametrów</span><span class="sxs-lookup"><span data-stu-id="0c10f-115">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="0c10f-116">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0c10f-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
