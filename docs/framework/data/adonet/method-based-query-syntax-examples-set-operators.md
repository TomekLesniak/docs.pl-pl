---
title: 'Przykłady składni zapytania oparte na metodzie: Ustaw operatory (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: f91d009e66f1f0da25e508994040d7e9f80fc681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147869"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a>Przykłady składni zapytania oparte na metodzie: Ustaw operatory (LINQ to DataSet)

W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Except%2A> operatorów,, <xref:System.Linq.Enumerable.Intersect%2A> i <xref:System.Linq.Enumerable.Union%2A> do wykonywania operacji porównania na podstawie wartości na zestawach wierszy danych.[ Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md) zobacz [porównywanie wierszy DataRows](comparing-datarows-linq-to-dataset.md) , aby uzyskać więcej informacji na temat <xref:System.Data.DataRowComparer> .  
  
 `FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).  
  
 W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="distinct"></a>Distinct  
  
### <a name="example"></a>Przykład  

 W tym przykładzie użyto <xref:System.Linq.Enumerable.Distinct%2A> metody, aby usunąć zduplikowane elementy w sekwencji.  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a>Z wyjątkiem  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Except%2A> metodę, aby zwrócić kontakty, które pojawiają się w pierwszej tabeli, ale nie w drugim.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a>Wspólnej  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Intersect%2A> metodę, aby zwrócić kontakty, które są wyświetlane w obu tabelach.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a>Unia  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Union%2A> metodę w celu zwrócenia unikatowych kontaktów z jednej z dwóch tabel.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a>Zobacz też

- [Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md)
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
- [Standardowe operatory zapytań — Omówienie (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Standardowe operatory zapytań — Omówienie (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
