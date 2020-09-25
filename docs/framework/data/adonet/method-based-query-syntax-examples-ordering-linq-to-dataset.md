---
title: 'Przykłady składni zapytania oparte na metodzie: porządkowanie (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 635b7f6e498e27ef8ca2e133df639f1010184a93
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197875"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a>Przykłady składni zapytania oparte na metodzie: porządkowanie (LINQ to DataSet)

W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.OrderBy%2A>  <xref:System.Linq.Enumerable.Reverse%2A> metod, i <xref:System.Linq.Enumerable.ThenBy%2A> do wykonywania zapytań <xref:System.Data.DataSet> i kolejności wyników przy użyciu składni zapytania metody.  
  
 `FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).  
  
 W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="orderby"></a>OrderBy  
  
### <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> metody z niestandardową funkcją porównującą, aby wykonać sortowanie ostatnich nazw bez uwzględniania wielkości liter.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a>Reverse  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Reverse%2A> metodę, aby utworzyć listę zamówień, która `OrderDate` jest wcześniejsza niż 20 lutego 2002.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> <xref:System.Linq.Enumerable.ThenBy%2A> metod i z niestandardowymi modułami porównującymi, aby najpierw sortować według cennika, a następnie wykonywać sortowanie nazw produktów bez uwzględniania wielkości liter.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a>Zobacz też

- [Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md)
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
- [Standardowe operatory zapytań — Omówienie (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Standardowe operatory zapytań — Omówienie (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
