---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274299"
---
# <a name="binding"></a>Wiązanie

Powiązanie usługi WMI  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa Binding nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa powiązania ma następujące właściwości.  
  
### <a name="bindingelements"></a>BindingElements  

 Typ danych: tablica BindingElement  
  
 Typ dostępu: tylko do odczytu  
  
 Kolekcja elementów powiązania implementowanych przez powiązanie.  
  
### <a name="closetimeout"></a>CloseTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu podanego na zakończenie operacji zamknięcia.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa powiązania.  
  
### <a name="namespace"></a>Przestrzeń nazw  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Przestrzeń nazw XML powiązania.  
  
### <a name="opentimeout"></a>OpenTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu podanego na zakończenie operacji otwarcia.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu podanego na zakończenie operacji odbioru.  
  
### <a name="scheme"></a>Schemat  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Schemat transportu URI używany przez fabryki kanałów i odbiorników, które są tworzone przez powiązanie.  
  
### <a name="sendtimeout"></a>Właściwości SendTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Interwał przeznaczony na zakończenie operacji wysyłania.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.Binding>
