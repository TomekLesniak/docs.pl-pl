---
title: 'Instrukcje: Rozwiązywanie konfliktów ze scaleniem wartości bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: fb77c4a23a4c4fa93dc55e63858ee41783c197ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166186"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a>Instrukcje: Rozwiązywanie konfliktów ze scaleniem wartości bazy danych

Aby uzgodnić różnice między oczekiwanymi i rzeczywistymi wartościami bazy danych przed próbą ponownego przesłania zmian, można użyć <xref:System.Data.Linq.RefreshMode.KeepChanges> programu do scalania wartości bazy danych z bieżącymi wartościami członków klienta. Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).  
  
> [!NOTE]
> We wszystkich przypadkach rekord na kliencie jest najpierw odświeżany przez pobranie zaktualizowanych danych z bazy danych. Ta akcja zapewnia, że kolejna próba aktualizacji nie powiedzie się na tych samych kontrolach współbieżności.  
  
## <a name="example"></a>Przykład  

 W tym scenariuszu <xref:System.Data.Linq.ChangeConflictException> wyjątek jest zgłaszany, gdy Użytkownik1 próbuje przesłać zmiany, ponieważ w międzyczasie została zmieniona kolumna asystenta i działu. W poniższej tabeli przedstawiono sytuację.  
  
||Menedżer|Pomocnik|Dział|  
|------|-------------|---------------|----------------|  
|Oryginalny stan bazy danych podczas wykonywania zapytania przez Użytkownik1 i.|Alfreds|Maria|Sales|  
|Użytkownik1 przygotowuje się do przesłania tych zmian.|Alfred||Marketing|  
|Do tego celu zostały już przesłane te zmiany.||Mary|Usługa|  
  
 Użytkownik1 decyduje się rozwiązać ten konflikt przez scalenie wartości bazy danych z bieżącymi wartościami członków klienta. Wynikiem tego jest to, że wartości bazy danych są zastępowane tylko wtedy, gdy bieżąca Grupa zmian również zmodyfikował tę wartość.  
  
 Gdy Użytkownik1 rozwiązuje konflikt przy użyciu <xref:System.Data.Linq.RefreshMode.KeepChanges> , wynik w bazie danych jest jak w poniższej tabeli:  
  
||Menedżer|Pomocnik|Dział|  
|------|-------------|---------------|----------------|  
|Nowy stan po rozwiązaniu konfliktu.|Alfred<br /><br /> (od Użytkownik1)|Mary<br /><br /> (od b do)|Marketing<br /><br /> (od Użytkownik1)|  
  
 Poniższy przykład pokazuje, jak scalić wartości bazy danych z bieżącymi wartościami członków klienta (chyba że klient również zmienił tę wartość). Nie występuje żadna Inspekcja ani Niestandardowa obsługa konfliktów poszczególnych członków.  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Rozwiązywanie konfliktów z zastąpieniem wartości bazy danych](how-to-resolve-conflicts-by-overwriting-database-values.md)
- [Instrukcje: Rozwiązywanie konfliktów z zachowaniem wartości bazy danych](how-to-resolve-conflicts-by-retaining-database-values.md)
- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
