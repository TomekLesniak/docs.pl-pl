---
title: 'Instrukcje: Zwracane zestawy wierszy'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: be03107db73ed230a87c2518e7825461afc2bc7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155747"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="133cd-102">Instrukcje: Zwracane zestawy wierszy</span><span class="sxs-lookup"><span data-stu-id="133cd-102">How to: Return Rowsets</span></span>

<span data-ttu-id="133cd-103">Ten przykład zwraca zestaw wierszy z bazy danych i zawiera parametr wejściowy do filtrowania wyniku.</span><span class="sxs-lookup"><span data-stu-id="133cd-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="133cd-104">Podczas wykonywania procedury składowanej, która zwraca zestaw wierszy, należy użyć klasy *wynik* , która przechowuje zwrot z procedury składowanej.</span><span class="sxs-lookup"><span data-stu-id="133cd-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="133cd-105">Aby uzyskać więcej informacji, zobacz [analizowanie LINQ to SQL kodzie źródłowym](analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="133cd-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="133cd-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="133cd-106">Example</span></span>  

 <span data-ttu-id="133cd-107">Poniższy przykład reprezentuje procedurę przechowywaną, która zwraca wiersze klientów i używa parametru wejściowego do zwrócenia tylko tych wierszy, które mają nazwę "Londyn" jako miasto klienta.</span><span class="sxs-lookup"><span data-stu-id="133cd-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="133cd-108">W przykładzie przyjęto założenie klasy wyliczalnej `CustomersByCityResult` .</span><span class="sxs-lookup"><span data-stu-id="133cd-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```sql  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="133cd-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="133cd-109">See also</span></span>

- [<span data-ttu-id="133cd-110">Procedury składowane</span><span class="sxs-lookup"><span data-stu-id="133cd-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="133cd-111">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="133cd-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
