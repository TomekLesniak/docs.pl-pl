---
title: Śledzenie argumentów i zmiennych
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: 85cecbfaf1db224152d4582325326f1f80e08266
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242906"
---
# <a name="variable-and-argument-tracking"></a>Śledzenie argumentów i zmiennych

Podczas śledzenia wykonywania przepływu pracy często warto wyodrębnić dane. Zapewnia to dodatkowy kontekst podczas uzyskiwania dostępu do rekordu śledzenia po wykonaniu. W programie [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] można wyodrębnić wszelką widoczną zmienną lub argument w zakresie dowolnego działania w przepływie pracy przy użyciu funkcji śledzenia. Profile śledzenia ułatwiają wyodrębnianie danych.  
  
## <a name="variables-and-arguments"></a>Zmienne i argumenty  

 Zmienne i argumenty są wyodrębniane, gdy działanie emituje ActivityStateRecord.  Zmienna jest dostępna do wyodrębnienia tylko wtedy, gdy znajduje się w zakresie działania. Zmienna do wyodrębnienia w ramach działania jest określana w następujący sposób:  
  
- Jeśli zmienna jest określona przez nazwę zmiennej, śledzenie szuka zmiennej w ramach bieżącego działania śledzonego i w działaniach nadrzędnych. Zmienna jest przeszukiwana w zakresie bieżącego działania i w zakresie nadrzędnym.  
  
- Jeśli zmienne do wyodrębnienia są określone przy użyciu Name = " \* ", wszystkie zmienne w monitorowanym działaniu są wyodrębniane. W tym przypadku zmienne, które znajdują się w zakresie, ale zdefiniowane w działaniach nadrzędnych, nie są wyodrębniane.  
  
 Podczas wyodrębniania argumentów wyodrębnione argumenty zależą od stanu działania. Gdy wykonywany jest stan działania, tylko `InArguments` są dostępne do wyodrębnienia. W przypadku każdego innego stanu działania (zamknięte, nieuszkodzone, anulowane) wszystkie argumenty, zarówno argument, jak i, są dostępne do wyodrębnienia.  
  
 W poniższym przykładzie przedstawiono zapytanie o stan działania, które wyodrębnia zmienne i argumenty podczas `Closed` emitowania rekordu śledzenia działania. Zmienne i argumenty mogą być wyodrębnione tylko z <xref:System.Activities.Tracking.ActivityStateRecord> i w ten sposób są subskrybowane w ramach profilu śledzenia przy użyciu <xref:System.Activities.Tracking.ActivityStateQuery> .  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a>Ochrona informacji przechowywanych w zmiennych i argumentach  

 Śledzona zmienna lub argument jest domyślnie widoczny dla środowiska uruchomieniowego WF. Deweloper przepływu pracy może chronić go przed dostępem, wykonując następujące czynności:  
  
1. Szyfruj wartość zmiennej.  
  
2. Kontroluj Tworzenie profilu śledzenia, aby zapobiec wyodrębnianiu zmiennej lub argumentu.  
  
3. W przypadku uczestników śledzenia niestandardowego upewnij się, że kod WF nie ujawnia poufnych informacji, które są przechowywane w zmiennych lub argumentach.  
  
## <a name="see-also"></a>Zobacz też

- [Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))
