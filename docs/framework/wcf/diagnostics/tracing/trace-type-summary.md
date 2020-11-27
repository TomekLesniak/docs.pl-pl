---
title: Podsumowanie typu śledzenia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259248"
---
# <a name="trace-type-summary"></a>Podsumowanie typu śledzenia

[Poziomy źródła](xref:System.Diagnostics.SourceLevels) definiują różne poziomy śledzenia: krytyczny, błąd, ostrzeżenie, informacje i pełne, a także zawiera opis `ActivityTracing` flagi, która przełącza dane wyjściowe granicy śledzenia i zdarzeń transferu aktywności.  
  
 Możesz również przejrzeć <xref:System.Diagnostics.TraceEventType> typy śladów, z których mogą być emitowane <xref:System.Diagnostics> .  
  
 W poniższej tabeli przedstawiono najważniejsze elementy.  
  
|Typ śledzenia|Opis|  
|----------------|-----------------|  
|Krytyczny|Błąd krytyczny lub awaria aplikacji.|  
|Błąd|Odwracalny błąd.|  
|Ostrzeżenie|Komunikat informacyjny.|  
|Informacje|Problem niekrytyczny.|  
|Pełny|Śledzenie debugowania.|  
|Rozpocznij|Rozpoczynanie logicznej jednostki przetwarzania.|  
|Wstrzymanie|Zawieszenie logicznej jednostki przetwarzania.|  
|Wznów|Wznawianie jednostki logicznej przetwarzania.|  
|Stop|Zatrzymywanie logicznej jednostki przetwarzania.|  
|Transfer|Zmiana tożsamości korelacji.|  
  
 Działanie jest zdefiniowane jako kombinacja powyższych typów śledzenia.  
  
 Poniżej znajduje się wyrażenie regularne, które definiuje idealne działanie w zakresie lokalnym (śledzenie źródła),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Oznacza to, że działanie musi spełniać następujące warunki.  
  
- Musi on być odpowiednio uruchamiany i zatrzymany przez uruchamianie i zatrzymywanie śledzenia  
  
- Musi mieć ślad transferu bezpośrednio poprzedzający śledzenie wstrzymania lub wznowienia  
  
- Nie może mieć żadnych śladów między śladami zawieszenia i wznowienia, jeśli istnieją takie ślady  
  
- Może to być dowolny i wiele ze śladów krytyczne/błąd/ostrzeżenie/informacja/pełny/transfer, o ile zostały spełnione poprzednie warunki  
  
 Poniżej znajduje się wyrażenie regularne, które definiuje idealne działanie w zakresie globalnym,  
  
`R+`  
  
 za pomocą języka R jest wyrażeniem regularnym dla działania w zakresie lokalnym. Spowoduje to przetłumaczenie na,  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
