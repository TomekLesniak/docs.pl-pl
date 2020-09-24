---
title: Tworzenie kolumn wyrażeń
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: ad14e4d3d6a1107f994d9536485257f9dc1851f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166849"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="6416a-102">Tworzenie kolumn wyrażeń</span><span class="sxs-lookup"><span data-stu-id="6416a-102">Creating Expression Columns</span></span>

<span data-ttu-id="6416a-103">Można zdefiniować wyrażenie dla kolumny, aby zawierało wartość obliczoną na podstawie innych wartości kolumn w tym samym wierszu lub z wartości kolumn obejmujących wiele wierszy w tabeli.</span><span class="sxs-lookup"><span data-stu-id="6416a-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="6416a-104">Aby zdefiniować wyrażenie do obliczenia, użyj <xref:System.Data.DataColumn.Expression%2A> Właściwości kolumny Target i Użyj <xref:System.Data.DataColumn.ColumnName%2A> właściwości, aby odwołać się do innych kolumn w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="6416a-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="6416a-105"><xref:System.Data.DataColumn.DataType%2A>Kolumna dla wyrażenia musi być odpowiednia dla wartości zwracanej przez wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="6416a-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="6416a-106">W poniższej tabeli przedstawiono kilka możliwych zastosowania kolumn wyrażeń w tabeli.</span><span class="sxs-lookup"><span data-stu-id="6416a-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="6416a-107">Typ wyrażenia</span><span class="sxs-lookup"><span data-stu-id="6416a-107">Expression type</span></span>|<span data-ttu-id="6416a-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="6416a-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="6416a-109">Porównanie</span><span class="sxs-lookup"><span data-stu-id="6416a-109">Comparison</span></span>|<span data-ttu-id="6416a-110">"Łącznie >= 500"</span><span class="sxs-lookup"><span data-stu-id="6416a-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="6416a-111">Obliczeń</span><span class="sxs-lookup"><span data-stu-id="6416a-111">Computation</span></span>|<span data-ttu-id="6416a-112">"CenaJednostkowa \* ilooć"</span><span class="sxs-lookup"><span data-stu-id="6416a-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="6416a-113">Agregacja</span><span class="sxs-lookup"><span data-stu-id="6416a-113">Aggregation</span></span>|<span data-ttu-id="6416a-114">Sum (cena)</span><span class="sxs-lookup"><span data-stu-id="6416a-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="6416a-115">Można ustawić właściwość **Expression** w istniejącym obiekcie **DataColumn** lub dodać właściwość jako trzeci argument do <xref:System.Data.DataColumn> konstruktora, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="6416a-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="6416a-116">Wyrażenia mogą odwoływać się do innych kolumn wyrażeń; jednak odwołanie cykliczne, w którym dwa wyrażenia odwołuje się nawzajem, wygeneruje wyjątek.</span><span class="sxs-lookup"><span data-stu-id="6416a-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="6416a-117">Aby uzyskać reguły dotyczące pisania wyrażeń, zobacz <xref:System.Data.DataColumn.Expression%2A> Właściwość klasy **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="6416a-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6416a-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6416a-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="6416a-119">Definicja schematu elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="6416a-119">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="6416a-120">Elementy DataTable</span><span class="sxs-lookup"><span data-stu-id="6416a-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="6416a-121">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6416a-121">ADO.NET Overview</span></span>](../ado-net-overview.md)
