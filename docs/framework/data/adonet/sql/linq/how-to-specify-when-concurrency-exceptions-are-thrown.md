---
title: 'Instrukcje: Określanie, kiedy są zgłaszane wyjątki współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 9d71ca82c3fe1abd23a82d952d38c3ea23a7f1c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197121"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Instrukcje: Określanie, kiedy są zgłaszane wyjątki współbieżności

W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.ChangeConflictException> wyjątek jest zgłaszany, gdy obiekty nie są aktualizowane z powodu nieoptymistycznych konfliktów współbieżności. Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).  
  
 Przed przesłaniem zmian do bazy danych można określić, kiedy mają być zgłaszane wyjątki współbieżności:  
  
- Zgłoś wyjątek przy pierwszym błędzie ( <xref:System.Data.Linq.ConflictMode.FailOnFirstConflict> ).  
  
- Zakończ wszystkie próby aktualizacji, zakumulowanie wszystkich błędów i Zgłoś błędy skumulowane w wyjątku ( <xref:System.Data.Linq.ConflictMode.ContinueOnConflict> ).  
  
 Gdy zostanie zgłoszony, <xref:System.Data.Linq.ChangeConflictException> wyjątek zapewnia dostęp do <xref:System.Data.Linq.ChangeConflictCollection> kolekcji. Ta kolekcja zawiera szczegółowe informacje dotyczące każdego konfliktu (zamapowane do pojedynczej nieudanej aktualizacji), w tym dostęp do <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> kolekcji. Konflikty każdego elementu członkowskiego są mapowane na pojedynczy element członkowski w aktualizacji, która nie mogła sprawdzić współbieżności.  
  
## <a name="example"></a>Przykład  

 Poniższy kod przedstawia przykłady obu wartości.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
