---
title: Usługa MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 7ef31a188e1564da47ea1e7323cdd4cd5ef5be60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236679"
---
# <a name="msmq"></a>Usługa MSMQ

W aplikacji MSMQ żadne dodatkowe działanie nie jest transferowane z kolejki w kolejce do usługi MSMQ i z usługi MSMQ do kanału znajdującego się w kolejce.  
  
 Ponadto identyfikator wiadomości MSMQ i Identyfikator komunikatu protokołu SOAP (wraz z IDENTYFIKATORem działania, jeśli taki istnieje) są śledzone jako część śladów kanałów umieszczonych w kolejce podczas operacji wysyłania.  
  
 Identyfikator wiadomości MSMQ i Identyfikator komunikatu protokołu SOAP (wraz z IDENTYFIKATORem działania, jeśli taki istnieje) są śledzone jako część śladów kanałów umieszczonych w kolejce dla operacji odbioru.  
  
 Wymagane transfery dla operacji Receive są wykonywane podobnie jak w przypadku wszystkich innych operacji transportu (odbieraj bajty — >procesu > operacji).
