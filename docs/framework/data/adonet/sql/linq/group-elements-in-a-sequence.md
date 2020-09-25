---
title: Grupowanie elementów w sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: d11d6f6231c1871cd54f0b0e3f6f862dc10b328b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194349"
---
# <a name="group-elements-in-a-sequence"></a>Grupowanie elementów w sekwencji

<xref:System.Linq.Enumerable.GroupBy%2A>Operator Grupuje elementy sekwencji. W poniższych przykładach użyto bazy danych Northwind.  
  
> [!NOTE]
> Wartości pustej kolumny w <xref:System.Linq.Enumerable.GroupBy%2A> zapytaniach mogą czasami zgłosić <xref:System.InvalidOperationException> . Aby uzyskać więcej informacji, zobacz sekcję "GroupBy InvalidOperationException" w temacie [Rozwiązywanie problemów](troubleshooting.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład partycjonowania `Products` przez `CategoryID` .  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa, <xref:System.Linq.Enumerable.Max%2A> Aby znaleźć maksymalną cenę jednostkową dla każdej z nich `CategoryID` .  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano średnią, aby znaleźć średnią `UnitPrice` dla każdej z nich `CategoryID` .  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa, <xref:System.Linq.Queryable.Sum%2A> Aby znaleźć sumę `UnitPrice` dla każdej z nich `CategoryID` .  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa, <xref:System.Linq.Queryable.Count%2A> Aby znaleźć liczbę wycofanych `Products` w każdym z nich `CategoryID` .  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie zastosowano następującą `where` klauzulę, aby znaleźć wszystkie kategorie, które mają co najmniej 10 produktów.  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład grupuje produkty według `CategoryID` i `SupplierID` .  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zwraca dwie sekwencje produktów. Pierwsza sekwencja zawiera produkty z ceną jednostkową mniejszą lub równą 10. Druga sekwencja zawiera produkty z ceną jednostkową większą niż 10.  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a>Przykład  

 <xref:System.Linq.Queryable.GroupBy%2A>Operator może przyjmować tylko jeden argument klucza. Jeśli zachodzi potrzeba pogrupowania przez więcej niż jeden klucz, należy utworzyć typ anonimowy, jak w poniższym przykładzie:  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
