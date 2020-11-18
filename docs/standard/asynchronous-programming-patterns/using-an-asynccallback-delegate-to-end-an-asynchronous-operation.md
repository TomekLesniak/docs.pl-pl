---
title: Używanie delegata AsyncCallback do kończenia operacji asynchronicznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: 55cc78bbfdda97a4d5ec8a2028fb3b0d7a9659e5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829131"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Używanie delegata AsyncCallback do kończenia operacji asynchronicznej
Aplikacje, które mogą wykonywać inne zadania podczas oczekiwania na wyniki operacji asynchronicznej, nie powinny blokować oczekiwania na zakończenie operacji. Użyj jednej z następujących opcji, aby kontynuować wykonywanie instrukcji podczas oczekiwania na zakończenie operacji asynchronicznej:  
  
- Użyj <xref:System.AsyncCallback> delegata, aby przetworzyć wyniki operacji asynchronicznej w osobnym wątku. Ta metoda jest przedstawiona w tym temacie.  
  
- Użyj <xref:System.IAsyncResult.IsCompleted%2A> właściwości <xref:System.IAsyncResult> zwróconej przez metodę **BEGIN**_OperationName_ operacji asynchronicznej, aby określić, czy operacja została ukończona. Aby zapoznać się z przykładem, który ilustruje to podejście, zobacz [sondowanie stanu operacji asynchronicznej](polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje użycie metod asynchronicznych w <xref:System.Net.Dns> klasie w celu pobrania informacji o systemie nazw domen (DNS) dla komputerów określonych przez użytkownika. Ten przykład tworzy <xref:System.AsyncCallback> delegata, który odwołuje się do `ProcessDnsInformation` metody. Ta metoda jest wywoływana jednokrotnie dla każdego żądania asynchronicznego dla informacji DNS.  
  
 Należy zauważyć, że host określony przez użytkownika jest przesyłany do <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> parametru. Aby zapoznać się z przykładem, który ilustruje definiowanie i używanie bardziej złożonego obiektu stanu, zobacz [Używanie delegata AsyncCallback i obiektu stanu](using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md)
- [Asynchroniczny wzorzec oparty na zdarzeniach — przegląd](event-based-asynchronous-pattern-overview.md)
- [Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult](calling-asynchronous-methods-using-iasyncresult.md)
- [Używanie delegata AsyncCallback i obiektu stanu](using-an-asynccallback-delegate-and-state-object.md)
