---
title: Kontrolowanie automatycznego uruchamiania hosta programu WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2033e693003d0b50bcdada428e4a5f451b3ad67e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255081"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Kontrolowanie automatycznego uruchamiania hosta programu WCF

Można kontrolować możliwość uruchamiania Windows Communication Foundation (WcfSvcHost.exe) dla projektu biblioteki usług WCF w przypadku debugowania innego projektu w tym samym rozwiązaniu programu Visual Studio zawierającym wiele projektów.  
  
 Aby to zrobić, kliknij prawym przyciskiem myszy projekt usługi WCF w **Eksplorator rozwiązań**, wybierz polecenie **Właściwości**, a następnie kliknij kartę **Opcje WCF** . **Uruchom hosta usługi WCF podczas debugowania innego projektu w tym samym rozwiązaniu** pole wyboru jest domyślnie włączone. Możesz wyczyścić to pole, aby Host usługi WCF dla danego projektu nie był uruchamiany, gdy inny projekt jest debugowany w tym samym rozwiązaniu.  
  
 To zachowanie nie ma wpływu na Debugowanie F5 ani Dodaj odwołanie do usługi funkcji dla tego projektu.  
  
 Ta opcja jest dostępna dla następujących projektów:  
  
- Projekt biblioteki usług WCF.  
  
- Projekt biblioteki usługi sekwencyjnego przepływu pracy.  
  
- Projekt biblioteki usługi przepływu pracy automatu Stanów.  
  
- Projekt biblioteki usługi zespolonej.  
  
## <a name="see-also"></a>Zobacz też

- [Host usługi WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
