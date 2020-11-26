---
title: Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: d70087a6dc1501f9a7f7ed057eae3dad181761ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248022"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności

Funkcja WCF nie gwarantuje kolejności, w której przetwarzane są komunikaty, chyba że źródłowy kanał to sesja.  Na przykład usługa WCF korzystająca z MsmqInputChannel, która nie jest kanałem sesji, nie przetwarza komunikatów w określonej kolejności. Istnieją pewne sytuacje, w których deweloper może chcieć wykonać przetwarzanie w kolejności, ale nie chce używać sesji. W tym temacie opisano sposób konfigurowania tego zachowania, gdy usługa jest uruchomiona w trybie pojedynczego współbieżności.  
  
## <a name="in-order-message-processing"></a>Przetwarzanie komunikatów w porządku  

 Dodano nowy atrybut o nazwie <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> <xref:System.ServiceModel.ServiceBehaviorAttribute> . Gdy <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> jest ustawiona na wartość true i <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> jest ustawiona na <xref:System.ServiceModel.ConcurrencyMode.Single> Komunikaty wysyłane do usługi, zostanie przetworzona w kolejności. Poniższy fragment kodu ilustruje sposób ustawiania tych atrybutów.  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Jeśli <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> jest ustawiona na inną wartość, <xref:System.InvalidOperationException> zostanie zgłoszony.  
  
## <a name="see-also"></a>Zobacz też

- [Sesje, tworzenie wystąpień i współbieżność](sessions-instancing-and-concurrency.md)
- [Współbieżność](../samples/concurrency.md)
