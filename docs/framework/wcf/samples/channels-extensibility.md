---
title: Rozszerzalność kanałów
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 1a734c305e2a6f2fc759647ab5bdf380f7c7eeee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253844"
---
# <a name="channels-extensibility"></a>Rozszerzalność kanałów

Ta sekcja zawiera przykłady demonstrujące kanały niestandardowe.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Lokalny kanał](local-channel.md)  
 Pokazuje kanał lokalny, kanał transportu WCF używany do komunikacji w ramach tej samej domeny aplikacji.  
  
 [Niezawodny bezpieczny profil](reliable-secure-profile.md)  
 Pokazuje, jak tworzyć usługi WCF i niezawodne bezpieczne profile (RSP).  
  
 [Niestandardowy dyspozytor kanału](custom-channel-dispatcher.md)  
 Demonstruje sposób tworzenia stosu kanału w sposób niestandardowy przez implementację <xref:System.ServiceModel.ServiceHostBase> bezpośrednio i sposób tworzenia niestandardowego dyspozytora kanału w środowisku hosta sieci Web.  
  
 [Kanał dzielący na fragmenty](chunking-channel.md)  
 Pokazuje, jak ograniczyć ilość pamięci używanej do buforowania dużych komunikatów wysyłanych za pomocą programu WCF.
  
 [HttpCookieSession](httpcookiesession.md)  
 Pokazuje, jak utworzyć niestandardowy kanał protokołu, aby używać plików cookie protokołu HTTP do zarządzania sesją.  
  
 [Niestandardowy element przechwytujący komunikaty](custom-message-interceptor.md)  
 Demonstruje sposób implementacji elementu niestandardowego powiązania, który tworzy fabryki kanałów i odbiorników kanałów do przechwytywania wszystkich komunikatów przychodzących i wychodzących w określonym punkcie w stosie czasu wykonywania.
