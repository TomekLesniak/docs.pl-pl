---
title: Zapisywanie aplikacji transakcyjnej
description: Napisz aplikację transakcyjną w programie .NET. Użyj jawnego lub niejawnego modelu programowania z klasą transakcji lub klasą TransactionScope, odpowiednio.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: b4cc33939128e61a69db319491a7d2d60ab9a819
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186670"
---
# <a name="writing-a-transactional-application"></a>Zapisywanie aplikacji transakcyjnej

Jako programista aplikacji transakcyjnej możesz skorzystać z dwóch modeli programowania dostarczonych przez <xref:System.Transactions> przestrzeń nazw, aby utworzyć transakcję. Można użyć jawnego modelu programowania przy użyciu <xref:System.Transactions.Transaction> klasy lub niejawnego modelu programowania, w którym transakcje są automatycznie zarządzane przez infrastrukturę, przy użyciu <xref:System.Transactions.TransactionScope> klasy. Zalecamy użycie niejawnego modelu transakcji na potrzeby programowania. Więcej informacji na temat używania zakresu transakcji można znaleźć w temacie [implementowanie niejawnej transakcji przy użyciu zakresu transakcji](implementing-an-implicit-transaction-using-transaction-scope.md) .  
  
 Oba modele obsługuje zatwierdzania transakcji, gdy program dociera spójnego stanu. Jeśli zatwierdzanie zakończy się powodzeniem, transakcja została ona niezawodnie dokonana. W przypadku niepowodzenia Zatwierdzanie transakcji przerywa. Jeśli program aplikacji nie może pomyślnie ukończyć transakcji, próbuje przerwać i cofnąć skutki transakcji.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
### <a name="creating-a-transaction"></a>Tworzenie transakcji  

 <xref:System.Transactions> Nazw zawiera dwa modele do tworzenia transakcji. Modele te zostały uwzględnione w następujących tematach.  
  
 [Implementowanie transakcji niejawnej przy użyciu zakresu transakcji](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Opisuje sposób, w jaki <xref:System.Transactions> przestrzeń nazw obsługuje tworzenie niejawnych transakcji przy użyciu <xref:System.Transactions.TransactionScope> klasy.  
  
 [Implementowanie transakcji jawnej przy użyciu CommitableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Opisuje sposób, w jaki <xref:System.Transactions> przestrzeń nazw obsługuje tworzenie jawnych transakcji przy użyciu <xref:System.Transactions.CommittableTransaction> klasy.  
  
### <a name="escalating-transaction-management"></a>Eskalowania zarządzania transakcji  

 Gdy transakcja musi uzyskać dostęp do zasobu w innej domenie aplikacji lub jeśli chcesz zarejestrować się w innym trwałym Menedżerze zasobów, transakcja zostanie automatycznie przekierowane, aby była zarządzana przez usługę MSDTC. Eskalacja transakcji znajduje się w temacie [Eskalacja zarządzania transakcjami](transaction-management-escalation.md) .  
  
### <a name="concurrency"></a>Współbieżność  

 Temat [Zarządzanie współbieżnością z DependentTransaction](managing-concurrency-with-dependenttransaction.md) pokazuje, jak współbieżność można osiągnąć między zadaniami asynchronicznymi przy użyciu <xref:System.Transactions.DependentTransaction> klasy.  
  
### <a name="com-interop"></a>Usługę Międzyoperacyjną modelu COM +  

 Temat [współdziałania z usługami przedsiębiorstwa i transakcji modelu COM+](interoperability-with-enterprise-services-and-com-transactions.md) ilustruje sposób, w jaki transakcje rozproszone mogą współdziałać z transakcjami modelu com+.  
  
### <a name="diagnostics"></a>Diagnostyka  

 [Ślady diagnostyczne](diagnostic-traces.md) opisują sposób użycia kodów śledzenia generowanych przez <xref:System.Transactions> infrastrukturę w celu rozwiązywania problemów z błędami w aplikacjach.  
  
### <a name="working-within-aspnet"></a>Praca w ramach programu ASP.NET  

 [W temacie using System. Transactions w ASP.NET](using-system-transactions-in-aspnet.md) opisano, jak można pomyślnie użyć <xref:System.Transactions> wewnątrz aplikacji ASP.NET.
