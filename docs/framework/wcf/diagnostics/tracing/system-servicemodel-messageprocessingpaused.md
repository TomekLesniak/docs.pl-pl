---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235119"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused

System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Opis  

 Wątki zostały przełączone podczas przetwarzania komunikatu.  
  
 Przetwarzanie komunikatów można wstrzymać z następujących powodów:  
  
- Właściwość ConcurrencyMode jest pojedyncza lub współużytkowana, a usługa przetwarza inną wiadomość.  
  
- Transakcja jest włączona, a usługa przetwarza inną transakcję.  
  
- Kontekst synchronizacji nie jest bieżący.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
