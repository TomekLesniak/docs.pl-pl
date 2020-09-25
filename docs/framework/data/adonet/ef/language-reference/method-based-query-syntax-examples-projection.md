---
title: Przykłady składni zapytania oparte na metodzie, projekcja
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: 32db3d0f85e525ad1850df59f0abe66bf82b137b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175788"
---
# <a name="method-based-query-syntax-examples-projection"></a>Przykłady składni zapytania oparte na metodzie, projekcja

W przykładach w tym temacie pokazano, jak za <xref:System.Linq.Enumerable.Select%2A> pomocą <xref:System.Linq.Enumerable.SelectMany%2A> metod i zbadać [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie. Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.  
  
 Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a>Wybierz pozycję  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano <xref:System.Linq.Queryable.Select%2A> metodę w celu zaprojektowania `Product.Name` `Product.ProductID` właściwości i w sekwencji typów anonimowych.  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.Select%2A> metodę, aby zwrócić sekwencję tylko nazw produktów.  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a>SelectMany  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.SelectMany%2A> metodę, aby wybrać wszystkie zamówienia, których `TotalDue` wartość jest mniejsza niż 500,00.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a>Przykład  

 W poniższym przykładzie użyto <xref:System.Linq.Enumerable.SelectMany%2A> metody, aby wybrać wszystkie zamówienia, w których zamówienie zostało wykonane w dniu 1 października 2002 lub nowszym.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
