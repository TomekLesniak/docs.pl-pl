---
title: Punkt końcowy
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288817"
---
# <a name="endpoint"></a>Punkt końcowy

Punkt końcowy  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa Endpoint definiuje następującą metodę.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Pobiera nazwę wystąpienia licznika wydajności operacji|  
  
## <a name="properties"></a>Właściwości  

 Klasa punktu końcowego ma następujące właściwości:  
  
### <a name="address"></a>Adres  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator URI zawierający adres punktu końcowego.  
  
### <a name="addressheaders"></a>AddressHeaders  

 Typ danych: tablica ciągów  
  
 Typ dostępu: tylko do odczytu  
  
 Kolekcja nagłówków adresów dołączonych do tego punktu końcowego.  
  
### <a name="addressidentity"></a>AddressIdentity  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Tożsamość punktu końcowego.  
  
### <a name="appdomainid"></a>AppDomainId  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator domeny aplikacji, która hostuje punkt końcowy.  
  
### <a name="behaviors"></a>Zachowania  

 Typ danych: tablica zachowań  
  
 Typ dostępu: tylko do odczytu  
  
 Kolekcja zachowań implementowanych przez ten punkt końcowy.  
  
### <a name="binding"></a>Wiązanie  

 Typ danych: powiązanie  
  
 Typ dostępu: tylko do odczytu  
  
 Powiązanie używane przez ten punkt końcowy.  
  
### <a name="contractname"></a>Nr kontraktu  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ciąg określający, który kontrakt jest ujawniany przez ten punkt końcowy.  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa wystąpienia liczników wydajności punktu końcowego.  
  
### <a name="listenuri"></a>ListenUri o wartości  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator URI, na którym nasłuchuje punkt końcowy.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Unikatowa nazwa tego punktu końcowego.  
  
### <a name="processid"></a>Identyfikator procesu  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator procesu, który hostuje punkt końcowy.  
  
### <a name="ref"></a>ref  

 Typ danych: kontrakt  
  
 Typ dostępu: tylko do odczytu  
  
 Kontrakt ujawniany przez ten punkt końcowy.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
