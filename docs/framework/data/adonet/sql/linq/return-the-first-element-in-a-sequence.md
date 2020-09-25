---
title: Zwracanie pierwszego elementu w sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 4506ef1a79c8f7e77160df4d55d0f93ee79f5a41
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200345"
---
# <a name="return-the-first-element-in-a-sequence"></a>Zwracanie pierwszego elementu w sekwencji

Użyj <xref:System.Linq.Enumerable.First%2A> operatora, aby zwrócić pierwszy element w sekwencji. Zapytania, które używają <xref:System.Linq.Enumerable.First%2A> są wykonywane od razu.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nie obsługuje <xref:System.Linq.Enumerable.Last%2A> operatora.  
  
## <a name="example"></a>Przykład  

 Poniższy kod umożliwia znalezienie pierwszego `Shipper` w tabeli:  
  
 W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind wyniki są  
  
 `ID = 1, Company = Speedy Express`.  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>Przykład  

 Poniższy kod umożliwia znalezienie pojedynczego `Customer` , który ma `CustomerID` BONAP.  
  
 W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind wyniki są następujące `ID = BONAP, Contact = Laurence Lebihan` .  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
