---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274052"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa element DeliveryRequirementsAttribute nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa element DeliveryRequirementsAttribute ma następujące właściwości:  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy powiązanie dla usługi obsługuje kontrakty.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy powiązanie obsługuje uporządkowane komunikaty.  
  
### <a name="targetcontract"></a>TargetContract  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Kontrakt, do którego ma zastosowanie.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
