---
title: Uczestnicy stanów trwałych
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: 0bff6cc8fafb1832dc4d0e33b754fe3adb81dcf6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246111"
---
# <a name="persistence-participants"></a>Uczestnicy stanów trwałych

Uczestnik trwałości może uczestniczyć w operacji trwałości (Save lub Load) wyzwalanej przez hosta aplikacji. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]Statki mające dwie klasy abstrakcyjne, **PersistenceParticipant** i **PersistenceIOParticipant**, których można użyć do utworzenia uczestnika trwałości. Uczestnik trwałości pochodzi z jednej z tych klas, implementuje metody zainteresowania, a następnie dodaje wystąpienie klasy do <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> kolekcji na <xref:System.ServiceModel.Activities.WorkflowServiceHost> . Host aplikacji może wyszukiwać takie rozszerzenia przepływu pracy podczas utrwalania wystąpienia przepływu pracy i wywoływać odpowiednie metody dla uczestników trwałości w odpowiednim czasie.  
  
 Poniższa lista zawiera opis zadań wykonywanych przez podsystem trwałości na różnych etapach operacji utrwalania (Save). Uczestnicy trwałości są używani w trzecim i czwartym etapie. Jeśli uczestnik jest uczestnikiem we/wy (uczestnik trwałości, który również uczestniczy w operacjach we/wy), uczestnik jest również używany na szóstym etapie.  
  
1. Gromadzi wartości wbudowane, w tym stan przepływu pracy, zakładki, zmapowane zmienne i sygnaturę czasową.  
  
2. Gromadzi wszystkich uczestników trwałości, którzy zostali dodani do kolekcji rozszerzeń skojarzonej z wystąpieniem przepływu pracy.  
  
3. Wywołuje <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> metodę zaimplementowaną przez wszystkich uczestników trwałości.  
  
4. Wywołuje <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> metodę zaimplementowaną przez wszystkich uczestników trwałości.  
  
5. Utrwalanie lub zapisywanie przepływu pracy w magazynie trwałości.  
  
6. Wywołuje <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> metodę we wszystkich uczestnikach we/wy trwałości. Jeśli uczestnik nie jest uczestnikiem we/wy, to zadanie jest pomijane. Jeśli odcinek trwałości jest transakcyjny, transakcja jest udostępniana w właściwości TRANSACTION. Current.  
  
7. Czeka na zakończenie wszystkich uczestników trwałości. Jeśli wszyscy uczestnicy pomyślnie zachowują dane wystąpienia, zatwierdziją transakcję.  
  
 Uczestnik trwałości pochodzi z klasy **PersistenceParticipant** i może implementować metody **CollectValues** i **MapValues** . Uczestnik we/wy o trwałości pochodzi z klasy **PersistenceIOParticipant** i może zaimplementować metodę **BeginOnSave** oprócz implementacji metod **CollectValues** i **MapValues** .  
  
 Każdy etap zostanie ukończony przed rozpoczęciem następnego etapu. Na przykład wartości są zbierane od **wszystkich** uczestników trwałości w pierwszym etapie. Następnie wszystkie wartości zebrane w pierwszym etapie są udostępniane wszystkim uczestnikom trwałości w drugim etapie na potrzeby mapowania. Następnie wszystkie wartości zbierane i mapowane na pierwszy i drugi etap są udostępniane dostawcy trwałości w trzecim etapie i tak dalej.  
  
 Poniższa lista zawiera opis zadań wykonywanych przez podsystem trwałości na różnych etapach operacji ładowania. Uczestnicy trwałości są używani w czwartym etapie. Uczestnicy operacji we/wy (uczestnicy trwałości, którzy również uczestniczą w operacjach we/wy) również są używani w trzecim etapie.  
  
1. Gromadzi wszystkich uczestników trwałości, którzy zostali dodani do kolekcji rozszerzeń skojarzonej z wystąpieniem przepływu pracy.  
  
2. Ładuje przepływ pracy z magazynu trwałości.  
  
3. Wywołuje <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> wszystkie uczestników we/wy o trwałości i czeka na zakończenie wszystkich uczestników trwałości. Jeśli odcinek trwałości jest transakcyjny, transakcja jest dostarczana w Transaction. Current.  
  
4. Ładuje wystąpienie przepływu pracy w pamięci na podstawie danych pobranych z magazynu trwałości.  
  
5. Wywołuje <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> każdy uczestnik trwałości.  
  
 Uczestnik trwałości pochodzi z klasy **PersistenceParticipant** i może zaimplementować metodę **PublishValues** . Uczestnik we/wy o trwałości pochodzi z klasy **PersistenceIOParticipant** i może zaimplementować metodę **BeginOnLoad** oprócz implementacji metody **PublishValues** .  
  
 Podczas ładowania wystąpienia przepływu pracy dostawca trwałości tworzy blokadę dla tego wystąpienia. Zapobiega to załadowaniu wystąpienia przez więcej niż jeden host w scenariuszu z wieloma węzłami. Jeśli spróbujesz załadować wystąpienie przepływu pracy, które zostało zablokowane, zobaczysz wyjątek podobny do następującego: wyjątek "System. ServiceModel. trwałości. InstanceLockException —: Żądana operacja nie mogła zostać ukończona, ponieważ nie można uzyskać blokady wystąpienia" 00000000-0000-0000-0000-000000000000 ". Ten błąd jest spowodowany wystąpieniem jednej z następujących sytuacji:  
  
- W scenariuszu obejmującym wiele węzłów wystąpienie jest ładowane przez innego hosta.  Istnieje kilka różnych sposobów rozwiązywania tych rodzajów konfliktów: przekazanie przetwarzania do węzła, który jest właścicielem blokady i ponawianie próby, lub wymuszenie obciążenia, co spowoduje, że inny host nie będzie mógł zapisać swojej pracy.  
  
- W scenariuszu z jednym węzłem i awarią hosta.  Po ponownym uruchomieniu hosta (proces odtwarzania lub utworzeniu nowej fabryki dostawców trwałości) Nowy host próbuje załadować wystąpienie, które jest nadal blokowane przez stary host, ponieważ blokada jeszcze nie wygasła.  
  
- W scenariuszu z jednym węzłem, a dane wystąpienie zostało przerwane w pewnym momencie i zostanie utworzone nowe wystąpienie dostawcy trwałości o innym IDENTYFIKATORze hosta.  
  
 Wartość limitu czasu blokady ma wartość domyślną wynoszącą 5 minut, podczas wywoływania należy określić inną wartość limitu czasu <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A> .  
  
## <a name="in-this-section"></a>W tej sekcji  
  
- [Instrukcje: Tworzenie niestandardowego uczestnika stanów trwałych](how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Zobacz też

- [Rozszerzalność magazynu](store-extensibility.md)
