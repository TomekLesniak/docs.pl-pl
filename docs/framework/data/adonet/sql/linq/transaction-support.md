---
title: Obsługa transakcji
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 1449f4d10d0feeec47ac17ffda91acb3e0da17ea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202204"
---
# <a name="transaction-support"></a>Obsługa transakcji

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje trzy różne modele transakcji. Poniżej wymieniono te modele w kolejności przeprowadzanych kontroli.  
  
## <a name="explicit-local-transaction"></a>Jawna transakcja lokalna  

 Gdy <xref:System.Data.Linq.DataContext.SubmitChanges%2A> jest wywoływana, jeśli <xref:System.Data.Linq.DataContext.Transaction%2A> Właściwość jest ustawiona na ( `IDbTransaction` ) transakcja, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> wywołanie jest wykonywane w kontekście tej samej transakcji.  
  
 Ponosisz odpowiedzialność za zatwierdzenie lub wycofanie transakcji po pomyślnym wykonaniu transakcji. Połączenie odpowiadające transakcji musi być zgodne z połączeniem używanym do konstruowania <xref:System.Data.Linq.DataContext> . Wyjątek jest generowany, jeśli używane jest inne połączenie.  
  
## <a name="explicit-distributable-transaction"></a>Jawna transakcja dystrybucyjna  

 Można wywołać [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] interfejsy API (w tym, ale nie ograniczone do <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ) w zakresie aktywnego <xref:System.Transactions.Transaction> . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wykrywa, czy wywołanie znajduje się w zakresie transakcji i nie tworzy nowej transakcji. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] w takim przypadku unika się również zamykania połączenia. Można wykonywać zapytania i <xref:System.Data.Linq.DataContext.SubmitChanges%2A> wykonania w kontekście takich transakcji.  
  
## <a name="implicit-transaction"></a>Niejawna transakcja  

 Po wywołaniu <xref:System.Data.Linq.DataContext.SubmitChanges%2A> , [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sprawdza, czy wywołanie znajduje się w zakresie <xref:System.Transactions.Transaction> lub czy `Transaction` Właściwość ( `IDbTransaction` ) jest ustawiona na lokalną transakcję uruchomioną przez użytkownika. Jeśli nie znajdzie żadnej transakcji, program [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uruchamia transakcję lokalną ( `IDbTransaction` ) i używa jej do wykonywania wygenerowanych poleceń SQL. Po pomyślnym zakończeniu wszystkich poleceń SQL zostanie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zatwierdzona lokalna transakcja i zwrócone.  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
- [Instrukcje: Przesyłanie danych nawiasów za pomocą transakcji](how-to-bracket-data-submissions-by-using-transactions.md)
