---
title: Licznik liczby elementów w sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164353"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Licznik liczby elementów w sekwencji

Użyj <xref:System.Linq.Enumerable.Count%2A> operatora, aby policzyć liczbę elementów w sekwencji.  
  
 Uruchomienie tego zapytania względem przykładowej bazy danych Northwind powoduje utworzenie danych wyjściowych `91` .  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zlicza liczbę `Customers` w bazie danych.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zlicza produkty w bazie danych, które nie zostały wycofane.  
  
 Uruchomienie tego przykładu w przypadku przykładowej bazy danych Northwind powoduje utworzenie danych wyjściowych `69` .  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania zagregowane](aggregate-queries.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
