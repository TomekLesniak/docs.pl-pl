---
title: 'Instrukcje: Zapytanie dotyczące informacji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166407"
---
# <a name="how-to-query-for-information"></a>Instrukcje: Zapytanie dotyczące informacji

Zapytania w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] używają tej samej składni co zapytania w LINQ. Jedyną różnicą jest to, że obiekty, do których odwołują się [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytania, są mapowane na elementy w bazie danych. Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczy zapytania zapisane w równoważne zapytania SQL i wysyła je do serwera w celu przetworzenia.  
  
 Niektóre funkcje zapytań LINQ mogą wymagać specjalnej uwagi w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplikacjach. Aby uzyskać więcej informacji, zobacz [pojęcia dotyczące zapytań](query-concepts.md).  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie pyta o listę klientów z usługi Londyn. W tym przykładzie `Customers` jest to tabela w przykładowej bazie danych Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie modelu obiektu](creating-the-object-model.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
- [wykonywanie zapytania w bazie danych](querying-the-database.md)
