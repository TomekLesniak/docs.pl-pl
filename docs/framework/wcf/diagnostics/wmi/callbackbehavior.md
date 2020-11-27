---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: cec9005a099247671dbebaacc0b242ca8d7a0144
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269651"
---
# <a name="callbackbehavior"></a>CallbackBehavior

CallbackBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa CallbackBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa CallbackBehavior ma następujące właściwości:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 W przypadku wartości true sesja jest automatycznie zamykana, gdy usługa zamyka sesję dupleksową.  
  
### <a name="concurrencymode"></a>Obsługują  

 Typ danych: ciąg  
Typ dostępu: tylko do odczytu  
  
 Określa, czy usługa obsługuje jeden wątek, wiele wątków lub wywołania współużytkowane.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość określająca, czy w sieci należy wysyłać nieznane dane serializacji.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Po włączeniu szczegółowe informacje o wyjątkach wywołania zwrotnego są dołączone do błędów zwróconych do usługi.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba elementów dozwolona w serializowanym obiekcie.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy do wybierania wątku wykonywania ma być używany bieżący kontekst synchronizacji.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy system lub aplikacja wymusza przetwarzanie nagłówka MustUnderstand protokołu SOAP.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
