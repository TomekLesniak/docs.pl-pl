---
title: Zdarzenia wyjątku ETW Thrown_V1
description: Wyświetl szczegółowe informacje o zdarzeniu ETW ExceptionThrown_V1. Dane zdarzenia, takie jak nazwy pól, typy danych i opisy, są przyznawane dla zgłaszanych wyjątków.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: c1ba994b291bd278a95e34beb0b02ed6581786e8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263480"
---
# <a name="exception-thrown_v1-etw-event"></a>Zdarzenia wyjątku ETW Thrown_V1

To zdarzenie przechwytuje informacje o wygenerowanych wyjątkach.  
  
 W poniższej tabeli przedstawiono słowo kluczowe, pod którym zdarzenie jest zgłaszane, oraz poziom zdarzenia. (Aby uzyskać więcej informacji, zobacz [słowa kluczowe i poziomy ETW CLR](clr-etw-keywords-and-levels.md)).  
  
|Słowo kluczowe do podniesienia zdarzenia|Poziom|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` 0x8000|Ostrzeżenie (2)|  
  
 W poniższej tabeli przedstawiono informacje o zdarzeniach.  
  
|Zdarzenie|Identyfikator zdarzenia|Wywoływane, gdy|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Generowany jest wyjątek zarządzany.|  
  
 W poniższej tabeli przedstawiono dane zdarzenia.  
  
|Nazwa pola|Typ danych|Opis|  
|----------------|---------------|-----------------|  
|Typ wyjątku|win: UnicodeString|Typ wyjątku; na przykład `System.NullReferenceException` .|  
|Komunikat o wyjątku|win: UnicodeString|Rzeczywisty komunikat o wyjątku.|  
|EIPCodeThrow|win: wskaźnik|Wskaźnik instrukcji, w którym wystąpił wyjątek.|  
|ExceptionHR|win: UInt32|Wyjątek [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|  
|ExceptionFlags|win: UInt16|0x01: HasInnerException (zobacz [zdarzenia ETW CLR](clr-etw-events.md) w dokumentacji Visual Basic).<br /><br /> 0x02: isnestexception.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (wskazuje, że stan procesu jest uszkodzony; zobacz [Obsługa wyjątków uszkodzonego stanu](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> 0x10: IsCLSCompliant (wyjątek pochodzący z <xref:System.Exception> jest zgodny ze specyfikacją CLS; w przeciwnym razie jest to niezgodne ze specyfikacją CLS).|  
|ClrInstanceID|win: UInt16|Unikatowy identyfikator wystąpienia CLR lub CoreCLR.|  
  
## <a name="see-also"></a>Zobacz też

- [Zdarzenia ETW CLR](clr-etw-events.md)
