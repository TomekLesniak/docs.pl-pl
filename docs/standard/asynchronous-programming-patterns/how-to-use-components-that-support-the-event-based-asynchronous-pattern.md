---
title: 'Instrukcje: Używanie składników obsługujących wzorzec asynchroniczny oparty na zdarzeniach'
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
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: 51394a49f12e8611ac6dba7eb93a6c9a9fae0cd0
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888805"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Instrukcje: Używanie składników obsługujących wzorzec asynchroniczny oparty na zdarzeniach
Wiele składników oferuje możliwość wykonywania pracy asynchronicznie. <xref:System.Media.SoundPlayer>Składniki i <xref:System.Windows.Forms.PictureBox> umożliwiają na przykład ładowanie dźwięków i obrazów "w tle", podczas gdy główny wątek nadal działa bez przeszkód.  
  
 Korzystanie z metod asynchronicznych na klasie, która obsługuje [oparte na zdarzeniach](event-based-asynchronous-pattern-overview.md) , można jak równie łatwo dołączać obsługę zdarzeń do zdarzenia **ukończenia** _MethodName_ przez składnik, podobnie jak w przypadku dowolnego innego zdarzenia. Po wywołaniu metody **asynchronicznej** _MethodName_ aplikacja będzie kontynuowała pracę bez przeszkód do momentu zgłoszenia zdarzenia _MethodName_**ukończone** . W programie obsługi zdarzeń można sprawdzić <xref:System.ComponentModel.AsyncCompletedEventArgs> parametr, aby określić, czy operacja asynchroniczna została ukończona pomyślnie, czy też została anulowana.  
  
 Aby uzyskać więcej informacji o korzystaniu z programów obsługi zdarzeń, zobacz [Omówienie obsługi zdarzeń](/dotnet/desktop/winforms/event-handlers-overview-windows-forms).  
  
 Poniższa procedura pokazuje, jak używać funkcji asynchronicznego ładowania obrazu <xref:System.Windows.Forms.PictureBox> formantu.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Aby włączyć formant PictureBox do asynchronicznego ładowania obrazu  
  
1. Utwórz wystąpienie <xref:System.Windows.Forms.PictureBox> składnika w formularzu.  
  
2. Przypisz do zdarzenia procedurę obsługi zdarzeń <xref:System.Windows.Forms.PictureBox.LoadCompleted> .  
  
     Sprawdź pod kątem błędów, które mogły wystąpić podczas pobierania asynchronicznego w tym miejscu. Jest to również miejsce, w którym można sprawdzić, czy jest to możliwe.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. Dodaj dwa przyciski, nazywane `loadButton` i `cancelLoadButton` , do formularza. Dodaj <xref:System.Windows.Forms.Control.Click> programy obsługi zdarzeń, aby rozpocząć i anulować pobieranie.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. Uruchom aplikację.  
  
     Po pobraniu obrazu będzie można swobodnie przenieść formularz, zminimalizować go i zmaksymalizować.  
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje: uruchamianie operacji w tle](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [Asynchroniczny wzorzec oparty na zdarzeniach — przegląd](event-based-asynchronous-pattern-overview.md)
