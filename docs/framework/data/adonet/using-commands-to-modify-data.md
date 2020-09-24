---
title: Używanie poleceń do modyfikacji danych
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: e2f61dbf74f28d026ae91a2bc8f5bb78530ffeac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177257"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="1ca24-102">Używanie poleceń do modyfikacji danych</span><span class="sxs-lookup"><span data-stu-id="1ca24-102">Using Commands to Modify Data</span></span>

<span data-ttu-id="1ca24-103">Za pomocą .NET Framework dostawcy danych można wykonać procedury składowane lub instrukcje języka definicji danych (na przykład CREATE TABLE i zmienić kolumnę), aby wykonać manipulowanie schematem bazy danych lub wykazu.</span><span class="sxs-lookup"><span data-stu-id="1ca24-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="1ca24-104">Te polecenia nie zwracają wierszy jako zapytania, dlatego obiekt **Command** udostępnia **ExecuteNonQuery** do przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="1ca24-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="1ca24-105">Oprócz używania **ExecuteNonQuery** do modyfikowania schematu, można również użyć tej metody do przetwarzania instrukcji SQL, które modyfikują dane, ale nie zwracają wierszy, takich jak INSERT, Update i DELETE.</span><span class="sxs-lookup"><span data-stu-id="1ca24-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="1ca24-106">Chociaż wiersze nie są zwracane przez metodę **ExecuteNonQuery** , parametry wejściowe i wyjściowe oraz zwracane wartości mogą być przekazywane i zwracane za pośrednictwem kolekcji **Parameters** obiektu **Command** .</span><span class="sxs-lookup"><span data-stu-id="1ca24-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ca24-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="1ca24-107">In This Section</span></span>  

 [<span data-ttu-id="1ca24-108">Aktualizowanie danych w źródle danych</span><span class="sxs-lookup"><span data-stu-id="1ca24-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="1ca24-109">Opisuje sposób wykonywania poleceń lub procedur składowanych, które modyfikują dane w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="1ca24-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="1ca24-110">Wykonywanie operacji katalogu</span><span class="sxs-lookup"><span data-stu-id="1ca24-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="1ca24-111">Opisuje sposób wykonywania poleceń, które modyfikują schemat bazy danych.</span><span class="sxs-lookup"><span data-stu-id="1ca24-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca24-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ca24-112">See also</span></span>

- [<span data-ttu-id="1ca24-113">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ca24-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="1ca24-114">Polecenia i parametry</span><span class="sxs-lookup"><span data-stu-id="1ca24-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="1ca24-115">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ca24-115">ADO.NET Overview</span></span>](ado-net-overview.md)
