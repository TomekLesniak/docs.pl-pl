---
title: 'Przykłady składni wyrażeń zapytania: projekcja (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
ms.openlocfilehash: e003c4356c2ab32814ac7a76ce008e21fb34192e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183172"
---
# <a name="query-expression-syntax-examples-projection--linq-to-dataset"></a>Przykłady składni wyrażeń zapytania: projekcja (LINQ to DataSet)

W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.Select%2A> <xref:System.Linq.Enumerable.SelectMany%2A> metod i do wykonywania zapytań <xref:System.Data.DataSet> przy użyciu składni wyrażeń zapytań.  
  
 `FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).  
  
 W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="select"></a>Wybierz pozycję  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Select%2A> metodę, aby zwrócić wszystkie wiersze z `Product` tabeli i wyświetlić nazwy produktów.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Enumerable.Select%2A> do zwracania sekwencji tylko nazw produktów.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## <a name="selectmany"></a>SelectMany  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano `From …, …` (odpowiednik <xref:System.Linq.Enumerable.SelectMany%2A> metody), aby wybrać wszystkie zamówienia, których `TotalDue` wartość jest mniejsza niż 500,00.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a>Przykład  

 W tym przykładzie użyto `From …, …` (odpowiednik <xref:System.Linq.Enumerable.SelectMany%2A> metody), aby wybrać wszystkie zamówienia, w których zamówienie zostało wykonane w dniu 1 października 2002 lub nowszym.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a>Przykład  

 W tym przykładzie zastosowano `From …, …` (odpowiednik <xref:System.Linq.Enumerable.SelectMany%2A> metody), aby wybrać wszystkie zamówienia, w których suma zamówienia jest większa niż 10000,00, i używa `From` przypisania, aby uniknąć podania łącznej liczby dwa razy.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a>Zobacz też

- [Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md)
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
- [Standardowe operatory zapytań — Omówienie (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Standardowe operatory zapytań — Omówienie (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
