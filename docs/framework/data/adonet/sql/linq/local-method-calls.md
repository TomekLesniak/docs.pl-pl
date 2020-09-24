---
title: Wywoływania metody lokalnej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 25aded1aa961e182e8d2d472fca4c5a84b501af1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166173"
---
# <a name="local-method-calls"></a>Wywoływania metody lokalnej

Wywołanie metody lokalnej to takie, które jest wykonywane w modelu obiektów. Wywołanie metody zdalnej to takie, które [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczy na SQL i przesyła do aparatu bazy danych w celu wykonania. Wywołania metody lokalnej są konieczne, gdy [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nie można przetłumaczyć wywołania na SQL. W przeciwnym razie <xref:System.InvalidOperationException> jest zgłaszany.  
  
## <a name="example-1"></a>Przykład 1  

 W poniższym przykładzie `Order` Klasa jest mapowana na tabelę Orders w przykładowej bazie danych Northwind. Lokalna metoda wystąpienia została dodana do klasy.  
  
 W zapytaniu 1 Konstruktor dla `Order` klasy jest wykonywany lokalnie. W zapytaniu 2, jeśli próba [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] przetłumaczenia `LocalInstanceMethod()` na SQL, próba nie powiedzie się i <xref:System.InvalidOperationException> zostanie zgłoszony wyjątek. Ale ponieważ [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapewnia obsługę wywołań metod lokalnych, Query2 nie zgłosi wyjątku.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
