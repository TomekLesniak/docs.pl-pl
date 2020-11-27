---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291118"
---
# <a name="activitytransfer"></a>ActivityTransfer

Zdarzenie transferu działania  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ActivityTransfer nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ActivityTransfer ma następujące właściwości:  
  
### <a name="activityid"></a>ActivityID  
  
- Typ danych: obiekt  
    Typ dostępu: tylko do odczytu  
  
- Identyfikator działania  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Typ danych: obiekt  
    Typ dostępu: tylko do odczytu  
  
- IDENTYFIKATOR powiązanego działania  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel.|
