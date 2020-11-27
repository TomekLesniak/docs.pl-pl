---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: e3716d42d479bcbdfd900b4fd2e335576a71574b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295603"
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute

ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceBehaviorAttribute nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceBehaviorAttribute ma następujące właściwości:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy sesja ma być automatycznie zamykana, gdy klient zamknie sesję wyjściową.  
  
### <a name="concurrencymode"></a>Obsługują  

 Typ danych: ciąg  
Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy usługa obsługuje jeden wątek, wiele wątków lub wywołania współużytkowane.  
  
### <a name="configurationname"></a>ConfigurationName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa konfiguracji usługi.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy wysyłać nieznane dane serializacji do sieci.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy informacje o zarządzanych wyjątkach mają być dołączane do szczegółowych informacji o błędach SOAP zwracanych do klientów na potrzeby debugowania.  
  
### <a name="instancecontextmode"></a>Tryb InstanceContextmode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, kiedy tworzony jest nowy obiekt usługi.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba elementów dozwolona w serializowanym obiekcie.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Atrybut nazwy usługi w języku WSDL.  
  
### <a name="namespace"></a>Przestrzeń nazw  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Docelowa przestrzeń nazw usługi w języku WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>Ustawion  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy obiekt usługi jest odtwarzany po zakończeniu bieżącej transakcji.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy oczekujące transakcje są kończone podczas zamykania bieżącej sesji.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa poziom izolacji transakcji.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Okres, w którym transakcja musi zostać zakończona.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy używać bieżącego kontekstu synchronizacji do wybierania wykonywania wątku.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy system lub aplikacja wymusza przetwarzanie nagłówka MustUnderstand protokołu SOAP.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
