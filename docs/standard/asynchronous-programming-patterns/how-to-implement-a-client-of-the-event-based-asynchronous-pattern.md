---
title: 'Instrukcje: Implementacja klienta wzorca asynchronicznego opartego na zdarzeniach'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 95997f219a08c131905cfc86b78e94c36f3ec851
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888818"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Instrukcje: Implementacja klienta wzorca asynchronicznego opartego na zdarzeniach
Poniższy przykład kodu ilustruje sposób użycia składnika, który jest zgodny z [omówieniem asynchronicznego wzorca opartego na zdarzeniach](event-based-asynchronous-pattern-overview.md). Formularz do tego przykładu używa `PrimeNumberCalculator` składnika opisanego w temacie [How to: Implementuj składnik, który obsługuje wzorzec asynchroniczny oparty na zdarzeniach](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Po uruchomieniu projektu, który używa tego przykładu, zobaczysz formularz "Kalkulator numeru początkowego" z siatką i dwoma przyciskami: **Uruchom nowe zadanie** i **Anuluj** . Możesz kliknąć przycisk **Rozpocznij nowe zadanie** kilka razy, a dla każdego kliknięcia, operacja asynchroniczna rozpocznie obliczenia, aby określić, czy losowo wygenerowany numer testu jest podstawowy. Formularz będzie okresowo wyświetlał postęp i wyniki przyrostowe. Każda operacja ma przypisany unikatowy identyfikator zadania. Wynik obliczeń jest wyświetlany w kolumnie **wynik** ; Jeśli numer testu nie jest znakiem, jest oznaczony jako **kompozytowy** i zostanie wyświetlony pierwszy dzielnik.  
  
 Wszystkie oczekujące operacje można anulować przy użyciu przycisku **Anuluj** . Można wprowadzić wiele zaznaczeń.  
  
> [!NOTE]
> Większość cyfr nie będzie podstawowa. Jeśli nie odnaleziono numeru początkowego po kilku ukończonych operacjach, wystarczy uruchomić więcej zadań i ostatecznie znaleźć liczby podstawowe.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
