---
title: 'Komunikacja podstawowa: Struktura połączenia'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: bd90bf75370776382b584388330e59a0701ed772
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277507"
---
# <a name="core-communications-connection-framework"></a>Komunikacja podstawowa: Struktura połączenia

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez platformę połączeń Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|CloseTimedOut|Upłynął limit czasu metody Close po określonym czasie. Zwiększ wartość limitu czasu, która jest przesyłana do wywołania, aby zamknąć lub zwiększyć wartość CloseTimeout dla powiązania. Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.|  
|ContentTypeMismatch|Określony typ zawartości został wysłany do usługi, która oczekiwał określonej wartości. Powiązania klienta i usługi mogą być niezgodne.|  
|DuplexChannelAbortedDuringOpen|Kanał dupleksowy do określonego przerwania w trakcie procesu otwierania.|  
|FramingValueNotAvailable|Nie można uzyskać dostępu do wartości, ponieważ nie jest ona w pełni zdekodowana.|  
|OperationAbortedDuringConnectionEstablishment|Operacja została zakończona podczas ustanawiania połączenia z określonym.|  
|ReceiveTimedOut2|Przekroczono limit czasu operacji odbierania po upływie określonego czasu. Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.|  
|SendCannotBeCalledAfterCloseOutputSession|Nie można wysyłać wiadomości w kanale po wywołaniu wywołaniu metody CloseOutputSession.|
