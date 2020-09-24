---
title: Co można zrobić za pomocą funkcji LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: a2e65cb558eec3cec21ea0efbcc66bb8c56ec7b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163924"
---
# <a name="what-you-can-do-with-linq-to-sql"></a>Co można zrobić za pomocą funkcji LINQ to SQL

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Program obsługuje wszystkie kluczowe możliwości, które należy oczekiwać jako deweloper SQL. Możesz wysyłać zapytania o informacje oraz wstawiać, aktualizować i usuwać informacje z tabel.  
  
## <a name="selecting"></a>Opcji  

 Wybór (*projekcja*) jest realizowany przez zapisanie zapytania LINQ we własnym języku programowania, a następnie wykonanie zapytania w celu pobrania wyników. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] samo tłumaczy wszystkie niezbędne operacje na niezbędne operacje SQL, które znasz. Aby uzyskać więcej informacji, zobacz [LINQ to SQL](index.md).  
  
 W poniższym przykładzie nazwy firmowe klientów z Londynie są pobierane i wyświetlane w oknie konsoli.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a>Wstawieniu  

 Aby wykonać instrukcję SQL `Insert` , wystarczy dodać obiekty do modelu obiektów, który został utworzony, i wywołać polecenie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Data.Linq.DataContext> .  
  
 W poniższym przykładzie nowy klient i informacje o kliencie są dodawane do `Customers` tabeli przy użyciu <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> .  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a>Aktualizowanie  

 Aby `Update` wejść do bazy danych, najpierw Pobierz element i edytuj go bezpośrednio w modelu obiektów. Po zmodyfikowaniu obiektu Wywołaj polecenie, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Data.Linq.DataContext> Aby zaktualizować bazę danych.  
  
 W poniższym przykładzie są pobierane wszyscy klienci z usługi Londyn. Nazwa miasta zostanie zmieniona z "Londyn" na "Londyn-metro". Na koniec <xref:System.Data.Linq.DataContext.SubmitChanges%2A> jest wywoływana w celu wysłania zmian do bazy danych.  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a>Usuwanie  

 Do `Delete` elementu, Usuń element z kolekcji, do której należy, a następnie Wywołaj metodę, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Data.Linq.DataContext> Aby zatwierdzić zmianę.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nie rozpoznaje operacji kaskadowego usuwania. Jeśli chcesz usunąć wiersz z tabeli zawierającej ograniczenia, zobacz [How to: delete Rows from a Database](how-to-delete-rows-from-the-database.md).  
  
 W poniższym przykładzie klient, który ma zostać `CustomerID` `98128` pobrany z bazy danych programu. Następnie po potwierdzeniu, że wiersz klienta został pobrany, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> jest wywoływana, aby usunąć ten obiekt z kolekcji. Na koniec <xref:System.Data.Linq.DataContext.SubmitChanges%2A> jest wywoływana, aby przesłać dalej operację usuwania do bazy danych.  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania](programming-guide.md)
- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Wprowadzenie](getting-started.md)
