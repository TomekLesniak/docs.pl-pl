---
title: Tworzenie kolumn typu AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9a979f39003e60c70c03206bd886bdd6827c82e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203725"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="44ad7-102">Tworzenie kolumn typu AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="44ad7-102">Creating AutoIncrement Columns</span></span>

<span data-ttu-id="44ad7-103">Aby zapewnić unikatowe wartości kolumn, można ustawić wartości kolumn, które mają być zwiększane automatycznie po dodaniu nowych wierszy do tabeli.</span><span class="sxs-lookup"><span data-stu-id="44ad7-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="44ad7-104">Aby utworzyć funkcję autozwiększania <xref:System.Data.DataColumn> , ustaw <xref:System.Data.DataColumn.AutoIncrement%2A> Właściwość kolumny na **true**.</span><span class="sxs-lookup"><span data-stu-id="44ad7-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="44ad7-105"><xref:System.Data.DataColumn>Następnie rozpoczyna się od wartości zdefiniowanej we <xref:System.Data.DataColumn.AutoIncrementSeed%2A> właściwości, a każdy wiersz dodaliśmy wartość kolumny **AutoIncrement** zwiększa się o wartość zdefiniowaną we <xref:System.Data.DataColumn.AutoIncrementStep%2A> Właściwości kolumny.</span><span class="sxs-lookup"><span data-stu-id="44ad7-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="44ad7-106">W przypadku kolumn typu **AutoIncrement** zalecamy, aby <xref:System.Data.DataColumn.ReadOnly%2A> Właściwość **DataColumn** była ustawiona na **wartość true**.</span><span class="sxs-lookup"><span data-stu-id="44ad7-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="44ad7-107">W poniższym przykładzie pokazano, jak utworzyć kolumnę rozpoczynającą się od wartości 200 i dodać przyrostowo w krokach 3.</span><span class="sxs-lookup"><span data-stu-id="44ad7-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="44ad7-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="44ad7-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="44ad7-109">Definicja schematu elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="44ad7-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="44ad7-110">Elementy DataTable</span><span class="sxs-lookup"><span data-stu-id="44ad7-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="44ad7-111">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="44ad7-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
