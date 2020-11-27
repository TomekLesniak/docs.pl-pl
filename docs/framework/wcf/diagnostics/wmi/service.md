---
title: Usługa
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273285"
---
# <a name="service"></a>Usługa

Usługa  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa usługi nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa usługi ma następujące właściwości:  
  
### <a name="baseaddresses"></a>BaseAddresses  

 Typ danych: tablica ciągów  
  
 Typ dostępu: tylko do odczytu  
  
 Adresy podstawowe używane przez usługę.  
  
### <a name="behaviors"></a>Zachowania  

 Typ danych: tablica zachowań  
  
 Typ dostępu: tylko do odczytu  
  
 Zachowania skojarzone z tą usługą.  
  
### <a name="configurationname"></a>ConfigurationName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa wystąpienia liczników wydajności usługi.  
  
### <a name="distinguishedname"></a>DistinguishedName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa usługi pod adresem.  
  
### <a name="extensions"></a>Rozszerzenia  

 Typ danych: tablica ciągów  
  
 Typ dostępu: tylko do odczytu  
  
 Konteksty wystąpienia dla rozszerzeń wystąpienia usługi.  
  
### <a name="metadata"></a>Metadane  

 Typ danych: tablica ciągów  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia metadanych usługi.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Unikatowa nazwa tej usługi.  
  
### <a name="namespace"></a>Przestrzeń nazw  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Przestrzeń nazw usługi.  
  
### <a name="opened"></a>Otworzyć  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Czas otwarcia usługi.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  

 Typ danych: tablica kanałów  
  
 Typ dostępu: tylko do odczytu  
  
 Kanały wychodzące z wystąpienia usługi.  
  
### <a name="processid"></a>Identyfikator procesu  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator procesu, który jest hostem usługi.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
