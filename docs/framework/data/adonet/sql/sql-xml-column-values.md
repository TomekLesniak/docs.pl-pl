---
title: Wartości kolumny SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177283"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="09855-102">Wartości kolumny SQL XML</span><span class="sxs-lookup"><span data-stu-id="09855-102">SQL XML Column Values</span></span>

<span data-ttu-id="09855-103">SQL Server obsługuje `xml` Typ danych, a deweloperzy mogą pobierać zestawy wyników, w tym typ, przy użyciu standardowego zachowania <xref:System.Data.SqlClient.SqlCommand> klasy.</span><span class="sxs-lookup"><span data-stu-id="09855-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="09855-104">`xml`Kolumnę można pobrać tylko w przypadku pobrania dowolnej kolumny ( <xref:System.Data.SqlClient.SqlDataReader> na przykład), ale jeśli chcesz korzystać z zawartości kolumny jako XML, musisz użyć <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="09855-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09855-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="09855-105">Example</span></span>  

 <span data-ttu-id="09855-106">Poniższa Aplikacja konsolowa wybiera dwa wiersze, `xml` z których każda zawiera kolumnę, z tabeli **Sales. Store** w bazie danych **AdventureWorks** do <xref:System.Data.SqlClient.SqlDataReader> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="09855-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="09855-107">Dla każdego wiersza wartość `xml` kolumny jest odczytywana przy użyciu <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> metody <xref:System.Data.SqlClient.SqlDataReader> .</span><span class="sxs-lookup"><span data-stu-id="09855-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="09855-108">Wartość jest przechowywana w <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="09855-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="09855-109">Należy pamiętać, że należy użyć <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> zamiast <xref:System.Data.IDataRecord.GetValue%2A> metody, jeśli chcesz ustawić zawartość dla <xref:System.Data.SqlTypes.SqlXml> zmiennej; <xref:System.Data.IDataRecord.GetValue%2A> zwraca wartość `xml` kolumny jako ciąg.</span><span class="sxs-lookup"><span data-stu-id="09855-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09855-110">Przykładowa baza danych **AdventureWorks** nie jest instalowana domyślnie podczas instalowania SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09855-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="09855-111">Można go zainstalować, uruchamiając Instalatora SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09855-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="09855-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="09855-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="09855-113">Dane XML w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="09855-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="09855-114">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="09855-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
