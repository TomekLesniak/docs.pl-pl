---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273948"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation

Mapuje usługę do punktu końcowego.  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceToEndpointAssociation nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceToEndpointAssociation ma następujące właściwości:  
  
### <a name="ref"></a>ref  

 Typ danych: usługa  
  
 Typ dostępu: tylko do odczytu  
Kwalifikatory: klucz  
  
 Usługa skojarzona z punktem końcowym.  
  
### <a name="ref"></a>ref  

 Typ danych: punkt końcowy  
  
 Typ dostępu: tylko do odczytu  
Kwalifikatory: klucz  
  
 Punkt końcowy skojarzony z usługą.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
