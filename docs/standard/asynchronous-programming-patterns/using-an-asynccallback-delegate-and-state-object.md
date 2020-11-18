---
title: Używanie delegata AsyncCallback i obiektu stanu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: 0a33c852d822e7d25d14ab17324459ec005853f9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829145"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Używanie delegata AsyncCallback i obiektu stanu
Gdy obiekt <xref:System.AsyncCallback> delegowany jest używany do przetwarzania wyników operacji asynchronicznej w osobnym wątku, można użyć obiektu stanu do przekazywania informacji między wywołaniami zwrotnymi i pobrania końcowego wyniku. W tym temacie pokazano, jak to zrobić, rozszerzając przykład przy [użyciu delegata AsyncCallback w celu zakończenia operacji asynchronicznej](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje użycie metod asynchronicznych w <xref:System.Net.Dns> klasie w celu pobrania informacji o systemie nazw domen (DNS) dla komputerów określonych przez użytkownika. Ten przykład definiuje i używa `HostRequest` klasy do przechowywania informacji o stanie. `HostRequest`Tworzony jest obiekt dla każdej nazwy komputera wprowadzonej przez użytkownika. Ten obiekt jest przesyłany do <xref:System.Net.Dns.BeginGetHostByName%2A> metody. `ProcessDnsInformation`Metoda jest wywoływana za każdym razem, gdy żądanie zostanie zakończone. `HostRequest`Obiekt zostanie pobrany przy użyciu <xref:System.IAsyncResult.AsyncState%2A> właściwości. `ProcessDnsInformation`Metoda używa `HostRequest` obiektu do przechowywania <xref:System.Net.IPHostEntry> zwracanych przez żądanie lub <xref:System.Net.Sockets.SocketException> zgłoszone przez żądanie. Po zakończeniu wszystkich żądań aplikacja wykonuje iterację `HostRequest` obiektów i wyświetla informacje DNS lub <xref:System.Net.Sockets.SocketException> komunikat o błędzie.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md)
- [Asynchroniczny wzorzec oparty na zdarzeniach — przegląd](event-based-asynchronous-pattern-overview.md)
- [Używanie delegata AsyncCallback do kończenia operacji asynchronicznej](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
