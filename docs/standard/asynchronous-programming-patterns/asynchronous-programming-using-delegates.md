---
title: Programowanie asynchroniczne przy użyciu delegatów
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 05e574536abe4eac823b7b74369f5b191724e5b5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889260"
---
# <a name="asynchronous-programming-using-delegates"></a>Programowanie asynchroniczne przy użyciu delegatów

Delegaty umożliwiają wywoływanie metody synchronicznej w sposób asynchroniczny. W przypadku wywołania delegata synchronicznie `Invoke` Metoda wywołuje metodę docelową bezpośrednio w bieżącym wątku. Jeśli `BeginInvoke` Metoda jest wywoływana, środowisko uruchomieniowe języka wspólnego (CLR) kolejkuje żądanie i natychmiast wraca do obiektu wywołującego. Metoda docelowa jest wywoływana asynchronicznie w wątku z puli wątków. Oryginalny wątek, który przesłał żądanie, jest bezpłatny, aby kontynuować wykonywanie równolegle z metodą docelową. Jeśli metoda wywołania zwrotnego została określona w wywołaniu `BeginInvoke` metody, metoda wywołania zwrotnego jest wywoływana, gdy metoda docelowa zostanie zakończona. W metodzie wywołania zwrotnego `EndInvoke` metoda uzyskuje wartość zwracaną oraz wszystkie parametry wejściowe/wyjściowe lub wyjściowe. Jeśli metoda wywołania zwrotnego nie zostanie określona podczas wywoływania `BeginInvoke` , `EndInvoke` można wywołać z wątku, który wywołał `BeginInvoke` .  
  
> [!IMPORTANT]
> Kompilatory powinny emitować klasy delegatów `Invoke` z `BeginInvoke` `EndInvoke` metodami, i przy użyciu podpisu delegata określonego przez użytkownika. `BeginInvoke`Metody i `EndInvoke` powinny być dekoracyjne. Ponieważ te metody są oznaczone jako natywne, środowisko CLR automatycznie udostępnia implementację w czasie ładowania klasy. Moduł ładujący gwarantuje, że nie są one zastępowane.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Wywołanie metod synchronicznych w sposób asynchroniczny](calling-synchronous-methods-asynchronously.md)  
 W tym artykule omówiono użycie delegatów do wykonywania wywołań asynchronicznych metod zwykłych i przedstawiono proste przykłady kodu, które pokazują cztery sposoby oczekiwania na zwrócenie wywołania asynchronicznego.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md)  
 Opisuje programowanie asynchroniczne w programie .NET.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Delegate>
