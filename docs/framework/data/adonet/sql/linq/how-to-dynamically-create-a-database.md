---
title: 'Instrukcje: Dynamiczne tworzenie bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: 95073eed3e0534a74272ee426ac6e329954c85a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173487"
---
# <a name="how-to-dynamically-create-a-database"></a>Instrukcje: Dynamiczne tworzenie bazy danych

W LINQ to SQL model obiektów jest mapowany do relacyjnej bazy danych. Mapowanie jest włączane przy użyciu mapowania opartego na atrybutach lub zewnętrznego pliku mapowania, aby opisać strukturę relacyjnej bazy danych. W obu scenariuszach jest wystarczająco dużo informacji o relacyjnej bazie danych, którą można utworzyć nowe wystąpienie bazy danych przy użyciu <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metody.  
  
 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>Metoda tworzy replikę bazy danych tylko do zakresu informacji zakodowanych w modelu obiektów. Mapowanie plików i atrybutów z modelu obiektów może nie zakodować wszystkiego o strukturze istniejącej bazy danych. Informacje o mapowaniu nie reprezentują zawartości funkcji zdefiniowanych przez użytkownika, procedur składowanych, wyzwalaczy ani ograniczeń check. To zachowanie jest wystarczające dla różnych baz danych.  
  
 Metody można użyć <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> w dowolnej liczbie scenariuszy, zwłaszcza jeśli znany dostawca danych, taki jak Microsoft SQL Server 2008 jest dostępny. Typowe scenariusze obejmują:  
  
- Tworzysz aplikację, która automatycznie instaluje się w systemie klienta.  
  
- Tworzysz aplikację kliencką, która wymaga lokalnej bazy danych do zapisania stanu offline.  
  
 Można również użyć <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metody z SQL Server przy użyciu pliku. mdf lub nazwy wykazu, w zależności od parametrów połączenia. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] program używa parametrów połączenia w celu zdefiniowania bazy danych, która ma zostać utworzona, oraz na serwerze, na którym ma zostać utworzona baza danych.  
  
> [!NOTE]
> Jeśli to możliwe, Użyj zintegrowanych zabezpieczeń systemu Windows do łączenia się z bazą danych, tak aby hasła nie były wymagane w parametrach połączenia.  
  
## <a name="example"></a>Przykład  

 Poniższy kod przedstawia przykład sposobu tworzenia nowej bazy danych o nazwie moje DVD. mdf.  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a>Przykład  

 Aby utworzyć bazę danych, można użyć modelu obiektów, wykonując następujące czynności:  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a>Przykład  

 Podczas kompilowania aplikacji, która automatycznie instaluje się w systemie klienta, sprawdź, czy baza danych już istnieje i upuść ją przed utworzeniem nowej. <xref:System.Data.Linq.DataContext>Klasa zawiera <xref:System.Data.Linq.DataContext.DatabaseExists%2A> metody i, <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> które ułatwiają przetworzenie tego procesu.  
  
 W poniższym przykładzie pokazano jeden z metod, których można użyć do wdrożenia tego podejścia:  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Zobacz też

- [Mapowanie oparte na atrybutach](attribute-based-mapping.md)
- [Mapowanie zewnętrzne](external-mapping.md)
- [Mapowania typów środowiska SQL-CLR](sql-clr-type-mapping.md)
- [Informacje uzupełniające](background-information.md)
- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
