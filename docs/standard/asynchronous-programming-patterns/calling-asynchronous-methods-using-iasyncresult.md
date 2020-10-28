---
title: Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 8e11f734410e266aa4c175551e8a3fbf5d9236c9
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888909"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult

Typy w bibliotekach .NET i bibliotekach klas innych firm mogą zapewnić metody, które pozwalają aplikacji kontynuować wykonywanie podczas wykonywania operacji asynchronicznych w wątkach innych niż główny wątek aplikacji. W poniższych sekcjach opisano i przedstawiono przykłady kodu, które przedstawiają różne sposoby wywoływania metod asynchronicznych, które używają <xref:System.IAsyncResult> wzorca projektowego.  
  
- [Blokowanie wykonywania aplikacji przez zakończenie operacji asynchronicznej](blocking-application-execution-by-ending-an-async-operation.md).  
  
- [Blokowanie wykonywania aplikacji przy użyciu AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
- [Sondowanie stanu operacji asynchronicznej](polling-for-the-status-of-an-asynchronous-operation.md).  
  
- [Użycie delegata AsyncCallback do zakończenia operacji asynchronicznej](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md)
- [Asynchroniczny wzorzec oparty na zdarzeniach — przegląd](event-based-asynchronous-pattern-overview.md)
