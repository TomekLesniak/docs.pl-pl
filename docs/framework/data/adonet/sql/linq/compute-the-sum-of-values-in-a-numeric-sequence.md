---
title: Obliczanie sumy wartości w sekwencji numerycznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3d160e2cce5f3e0a7eea305657260b6fa4ded7fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164444"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Obliczanie sumy wartości w sekwencji numerycznej

Użyj <xref:System.Linq.Enumerable.Sum%2A> operatora, aby obliczyć sumę wartości liczbowych w sekwencji.  
  
 Zwróć uwagę na następujące cechy `Sum` operatora w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :  
  
- Operator agregujący standardowego operatora zapytania `Sum` ma wartość zero dla pustej sekwencji lub sekwencji zawierającej tylko wartości null. W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] semantyka SQL pozostaje niezmieniona. Z tego powodu program `Sum` zwraca wartość null zamiast zero dla pustej sekwencji lub dla sekwencji zawierającej tylko wartości null.  
  
- Ograniczenia SQL dotyczące wyników pośrednich stosują się do agregacji w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Suma 32-bitowych liczb całkowitych nie jest obliczana przy użyciu 64-bitowych wyników, a przepełnienie może wystąpić w przypadku [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczenia `Sum` . Taka możliwość istnieje, nawet jeśli implementacja standardowego operatora zapytań nie powoduje przepełnienia odpowiedniej sekwencji w pamięci.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład umożliwia znalezienie łącznego frachtu wszystkich zamówień w `Order` tabeli.  
  
 W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `64942.6900` .  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład umożliwia znalezienie łącznej liczby jednostek w kolejności dla wszystkich produktów.  
  
 W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind dane wyjściowe to: `780` .  
  
 Należy zauważyć, że należy rzutować `short` typy (na przykład `UnitsOnOrder` ), ponieważ `Sum` nie ma przeciążenia dla krótkich typów.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania zagregowane](aggregate-queries.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
