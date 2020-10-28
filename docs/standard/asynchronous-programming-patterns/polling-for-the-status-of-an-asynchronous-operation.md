---
title: Sondowanie stanu operacji asynchronicznych
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: c73ee50c67034feed07a4869deb0a32342bb45e5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888740"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Sondowanie stanu operacji asynchronicznych
Aplikacje, które mogą wykonywać inne zadania podczas oczekiwania na wyniki operacji asynchronicznej, nie powinny blokować oczekiwania na zakończenie operacji. Użyj jednej z następujących opcji, aby kontynuować wykonywanie instrukcji podczas oczekiwania na zakończenie operacji asynchronicznej:  
  
- Użyj <xref:System.IAsyncResult.IsCompleted%2A> właściwości <xref:System.IAsyncResult> zwróconej przez metodę **BEGIN**_OperationName_ operacji asynchronicznej, aby określić, czy operacja została ukończona. Takie podejście jest nazywane sondami i przedstawiono w tym temacie.  
  
- Użyj <xref:System.AsyncCallback> delegata, aby przetworzyć wyniki operacji asynchronicznej w osobnym wątku. Przykład demonstrujący to podejście, zobacz [Używanie delegata AsyncCallback do kończenia operacji asynchronicznej](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje użycie metod asynchronicznych w <xref:System.Net.Dns> klasie w celu pobrania informacji o systemie nazw domen dla komputera określonego przez użytkownika. Ten przykład uruchamia asynchroniczną operację, a następnie drukuje kropki (".") w konsoli do momentu ukończenia operacji. Należy zauważyć, że **wartość null** ( **Nothing** w Visual Basic) nie jest przesyłana do <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> parametrów i, <xref:System.Object> ponieważ te argumenty nie są wymagane podczas korzystania z tego podejścia.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md)
- [Asynchroniczny wzorzec oparty na zdarzeniach — przegląd](event-based-asynchronous-pattern-overview.md)
