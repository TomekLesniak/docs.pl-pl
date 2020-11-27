---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 48d26bfa9074fd605e3545579f0bdc2744dfc7d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267862"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase

MsmqBindingElementBase  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa MsmqBindingElementBase nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa MsmqBindingElementBase ma następujące właściwości:  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator URI, który zawiera lokalizację kolejki utraconych wiadomości dla każdej aplikacji, miejsce, w której znajdują się komunikaty, które wygasły lub które nie zostały przekazane.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wyliczenia wskazująca typ używanej kolejki utraconych wiadomości.  
  
### <a name="durable"></a>Trwałość  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy komunikaty przetwarzane przez to powiązanie są trwałe czy nietrwałe.  
  
### <a name="exactlyonce"></a>ExactlyOnce  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna wskazująca, czy komunikaty przetwarzane przez to powiązanie są odbierane dokładnie raz.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba ponownych prób dostarczenia komunikatów do aplikacji odbiorczej.  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia obsługi skażonych komunikatów.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba natychmiastowych ponownych prób w komunikacie odczytywanym z kolejki aplikacji.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca czas opóźnienia między kolejnymi próbami dostarczenia komunikatu, którego nie można było dostarczyć natychmiast.  
  
### <a name="timetolive"></a>TimeToLive  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu, który wskazuje, jak długo komunikaty przetwarzane przez to powiązanie mogą znajdować się w kolejce przed ich wygaśnięciem.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna wskazująca, czy komunikaty przetwarzane przez to powiązanie powinny być śledzone.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna wskazująca, czy kopie komunikatów przetwarzanych przez to powiązanie powinny być przechowywane w kolejce dziennika źródła.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
