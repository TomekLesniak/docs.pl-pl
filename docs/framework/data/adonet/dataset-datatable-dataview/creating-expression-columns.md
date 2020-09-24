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
# <a name="creating-expression-columns"></a>Tworzenie kolumn wyrażeń

Można zdefiniować wyrażenie dla kolumny, aby zawierało wartość obliczoną na podstawie innych wartości kolumn w tym samym wierszu lub z wartości kolumn obejmujących wiele wierszy w tabeli. Aby zdefiniować wyrażenie do obliczenia, użyj <xref:System.Data.DataColumn.Expression%2A> Właściwości kolumny Target i Użyj <xref:System.Data.DataColumn.ColumnName%2A> właściwości, aby odwołać się do innych kolumn w wyrażeniu. <xref:System.Data.DataColumn.DataType%2A>Kolumna dla wyrażenia musi być odpowiednia dla wartości zwracanej przez wyrażenie.  
  
 W poniższej tabeli przedstawiono kilka możliwych zastosowania kolumn wyrażeń w tabeli.  
  
|Typ wyrażenia|Przykład|  
|---------------------|-------------|  
|Porównanie|"Łącznie >= 500"|  
|Obliczeń|"CenaJednostkowa * ilooć"|  
|Agregacja|Sum (cena)|  
  
 Można ustawić właściwość **Expression** w istniejącym obiekcie **DataColumn** lub dodać właściwość jako trzeci argument do <xref:System.Data.DataColumn> konstruktora, jak pokazano w poniższym przykładzie.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Wyrażenia mogą odwoływać się do innych kolumn wyrażeń; jednak odwołanie cykliczne, w którym dwa wyrażenia odwołuje się nawzajem, wygeneruje wyjątek. Aby uzyskać reguły dotyczące pisania wyrażeń, zobacz <xref:System.Data.DataColumn.Expression%2A> Właściwość klasy **DataColumn** .  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Definicja schematu elementu DataTable](datatable-schema-definition.md)
- [Elementy DataTable](datatables.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
