---
title: 'Optymistyczna współbieżność: Omówienie'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: 7a1bc23d9f012b2f3541c1411a25b7527e696873
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169404"
---
# <a name="optimistic-concurrency-overview"></a>Optymistyczna współbieżność: Omówienie

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje optymistyczną kontrolę współbieżności. W poniższej tabeli opisano terminy, które dotyczą optymistycznej współbieżności w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dokumentacji:  
  
|Terminologia|Opis|  
|-----------|-----------------|  
|współbieżność|Sytuacja, w której co najmniej dwóch użytkowników w tym samym czasie próbuje zaktualizować ten sam wiersz bazy danych.|  
|konflikt współbieżności|Sytuacja, w której dwóch lub więcej użytkowników w tym samym czasie próbuje przesłać wartości powodujące konflikt do jednej lub kilku kolumn w wierszu.|  
|formant współbieżności|Technika służąca do rozwiązywania konfliktów współbieżności.|  
|Optymistyczna kontrola współbieżności|Technika, która najpierw sprawdza, czy inne transakcje zmieniły wartości w wierszu przed umożliwieniem przesłania zmian.<br /><br /> Różni się od *pesymistycznej kontroli współbieżności*, która blokuje rekord, aby uniknąć konfliktów współbieżności.<br /><br /> Kontrola *optymistyczna* jest w ten sposób uznawana, ponieważ uwzględnia szanse jednej transakcji zakłócające, że jest to mało prawdopodobne.|  
|Rozwiązywanie konfliktów|Proces odświeżania elementu powodującego konflikt przez ponowne wykonywanie zapytania względem bazy danych, a następnie Uzgadnianie różnic.<br /><br /> Po odświeżeniu obiektu narzędzie do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] śledzenia zmian zawiera następujące dane:<br /><br /> — Wartości początkowo pobrane z bazy danych i używane do sprawdzania aktualizacji.<br />— Nowe wartości bazy danych z kolejnego zapytania.<br /><br /> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] następnie decyduje o tym, czy obiekt jest w konflikcie (czyli czy co najmniej jedna jego wartość członkowska została zmieniona). Jeśli obiekt jest w konflikcie, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] następnie należy określić, który z jego elementów członkowskich jest w konflikcie.<br /><br /> Wszelkie konflikty elementów członkowskich, które [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] są odnajdywane, zostaną dodane do listy konfliktów.|  
  
 W [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelu obiektów występuje *konflikt optymistycznej współbieżności* , gdy spełniony jest oba z następujących warunków:  
  
- Klient próbuje przesłać zmiany do bazy danych.  
  
- Co najmniej jedna wartość sprawdzania aktualizacji została zaktualizowana w bazie danych od czasu ostatniego odczytu przez klienta.  
  
 Rozwiązanie tego konfliktu obejmuje odnajdywanie, które elementy członkowskie obiektu są w konflikcie, a następnie decydowanie o tym, co chcesz zrobić.  
  
> [!NOTE]
> Tylko członkowie zamapowane jako <xref:System.Data.Linq.Mapping.UpdateCheck.Always> lub <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> uczestniczą w sprawdzaniu współbieżności optymistycznej. Nie jest wykonywane żadne sprawdzenie dla elementów członkowskich oznaczonych <xref:System.Data.Linq.Mapping.UpdateCheck.Never> . Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## <a name="example"></a>Przykład  

 Na przykład w poniższym scenariuszu Użytkownik1 rozpocznie się przygotowywanie aktualizacji przez przeszukiwanie wiersza w bazie danych. Użytkownik1 odbiera wiersz o wartościach Alfreds, Maria i Sales.  
  
 Użytkownik1 chce zmienić wartość kolumny Manager na Alfred i wartość kolumny działu na marketing. Zanim Użytkownik1 będzie mógł przesłać te zmiany, nastąpiło przesłanie zmian do bazy danych. W związku z tym teraz wartość kolumny asystenta została zmieniona na Mary i wartość kolumny dział na usługa.  
  
 Gdy Użytkownik1 podejmie teraz próbę przesłania zmian, przesłanie nie powiedzie się i <xref:System.Data.Linq.ChangeConflictException> zostanie zgłoszony wyjątek. Ten wynik występuje, ponieważ wartości bazy danych dla kolumny asystenta i działu nie są oczekiwane. Elementy członkowskie reprezentujące kolumny asystenta i działu są w konflikcie. Poniższa tabela zawiera podsumowanie sytuacji.  
  
||Menedżer|Pomocnik|Dział|  
|------|-------------|---------------|----------------|  
|Stan pierwotny|Alfreds|Maria|Sales|  
|Użytkownik1|Alfred||Marketing|  
|Użytkownik2||Mary|Usługa|  
  
 Można rozwiązać konflikty, takie jak na różne sposoby. Aby uzyskać więcej informacji, zobacz [How to: Manage konflikts Change](how-to-manage-change-conflicts.md).  
  
## <a name="conflict-detection-and-resolution-checklist"></a>Lista kontrolna wykrywania i rozwiązywania konfliktów  

 Możesz wykrywać i rozwiązywać konflikty na dowolnym poziomie szczegółowości. Z jednej najwyższej klasy można rozwiązać wszystkie konflikty na jeden z trzech sposobów (zobacz <xref:System.Data.Linq.RefreshMode> ) bez dodatkowych zagadnień. Z drugiej najwyższej klasy można wyznaczyć określoną akcję dla każdego typu konfliktu dla każdego elementu członkowskiego powodującego konflikt.  
  
- Określ lub skoryguj <xref:System.Data.Linq.Mapping.UpdateCheck> Opcje w modelu obiektów.  
  
     Aby uzyskać więcej informacji, zobacz [How to: Określanie, które elementy członkowskie są testowane pod kątem konfliktów współbieżności](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
- W bloku try/catch wywołania do <xref:System.Data.Linq.DataContext.SubmitChanges%2A> Określ, w którym punkcie mają być zgłaszane wyjątki.  
  
     Aby uzyskać więcej informacji, zobacz [How to: Określ, kiedy są zgłaszane wyjątki współbieżności](how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
- Określ, ile szczegółów konfliktów chcesz pobrać, i odpowiednio Dołącz kod w bloku try/catch.  
  
     Aby uzyskać więcej informacji, zobacz [How to: pobieranie informacji o konflikcie jednostki](how-to-retrieve-entity-conflict-information.md) i [instrukcje: pobieranie informacji o konflikcie elementu członkowskiego](how-to-retrieve-member-conflict-information.md).  
  
- Uwzględnij w `try` / `catch` kodzie sposób, w jaki chcesz rozwiązać różne odnajdywane konflikty.  
  
     Aby uzyskać więcej informacji, zobacz [jak: Rozwiązywanie konfliktów przez zachowywanie wartości bazy danych](how-to-resolve-conflicts-by-retaining-database-values.md), [instrukcje: Rozwiązywanie konfliktów przez zastępowanie wartości bazy danych](how-to-resolve-conflicts-by-overwriting-database-values.md)i [instrukcje: Rozwiązywanie konfliktów przez scalanie z wartościami bazy danych](how-to-resolve-conflicts-by-merging-with-database-values.md).  
  
## <a name="linq-to-sql-types-that-support-conflict-discovery-and-resolution"></a>Typy LINQ to SQL obsługujące wykrywanie i rozwiązywanie konfliktów  

 Klasy i funkcje do obsługi rozwiązywania konfliktów w optymistycznej współbieżności w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obejmują następujące elementy:  
  
- <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.MemberChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictException?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.RefreshMode?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
