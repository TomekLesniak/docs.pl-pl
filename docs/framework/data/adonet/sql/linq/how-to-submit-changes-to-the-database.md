---
title: 'Instrukcje: Przesyłanie zmian do bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
ms.openlocfilehash: 5952cce5469d7a7e13e8b896f91ea1279fd62d8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197043"
---
# <a name="how-to-submit-changes-to-the-database"></a>Instrukcje: Przesyłanie zmian do bazy danych

Bez względu na liczbę zmian dokonanych w obiektach, zmiany są wprowadzane tylko do replik w pamięci. Nie wprowadzono żadnych zmian w rzeczywistych danych w bazie danych. Zmiany nie są przekazywane do serwera, dopóki nie zostanie jawnie wywołana <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Data.Linq.DataContext> .  
  
 Po nadaniu tego wywołania <xref:System.Data.Linq.DataContext> próbuje przetłumaczyć zmiany na równoważne polecenia SQL. Możesz użyć własnej logiki niestandardowej, aby przesłonić te działania, ale kolejność przesłania jest zorganizowany przez usługę <xref:System.Data.Linq.DataContext> znanego jako *procesor zmian*. Sekwencja zdarzeń jest następująca:  
  
1. Po wywołaniu <xref:System.Data.Linq.DataContext.SubmitChanges%2A> , [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sprawdza zestaw znanych obiektów, aby określić, czy zostały do nich dołączone nowe wystąpienia. Jeśli mają, nowe wystąpienia są dodawane do zestawu śledzonych obiektów.  
  
2. Wszystkie obiekty, które mają oczekujące zmiany są uporządkowane w kolejności obiektów na podstawie zależności między nimi. Obiekty, których zmiany zależą od innych obiektów, są sekwencjonowane po ich zależnościach.  
  
3. Natychmiast przed przesłaniem rzeczywistych zmian program [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uruchamia transakcję w celu hermetyzacji szeregu poszczególnych poleceń.  
  
4. Zmiany w obiektach są tłumaczone pojedynczo do poleceń SQL i wysyłane do serwera.  
  
 W tym momencie wszystkie błędy wykryte przez bazę danych powodują zatrzymanie procesu wysyłania i zgłaszany jest wyjątek. Wszystkie zmiany w bazie danych są wycofywane tak, jakby nie miały żadnych przesłanych elementów. <xref:System.Data.Linq.DataContext>Nadal ma pełne nagranie wszystkich zmian. W związku z tym możesz spróbować rozwiązać problem i <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ponownie wywołać, jak w poniższym przykładzie kodu.  
  
## <a name="example"></a>Przykład  

 Po pomyślnym zakończeniu transakcji w <xref:System.Data.Linq.DataContext> celu zaakceptowania zmian w obiektach zostaną one zignorowane.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Wykrywanie i rozwiązywanie powodujących konflikt przesłań](how-to-detect-and-resolve-conflicting-submissions.md)
- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
- [Pobieranie przykładowych baz danych](downloading-sample-databases.md)
- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
