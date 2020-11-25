---
title: IReferenceAppId — Interfejs
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728618"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId — Interfejs

Reprezentuje odwołanie do unikatowego identyfikatora aplikacji w bieżącym zakresie.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Pobiera wskaźnik do ciągu reprezentującego identyfikator kodu dla aplikacji, do której się odwołuje `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|Ustawia identyfikator kodu dla aplikacji, do której się odwołuje `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|Pobiera wskaźnik interfejsu do `IEnumReferenceIdentity` wystąpienia zawierającego `IReferenceIdentity` wystąpienia, które reprezentują elementy członkowskie tego elementu `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|Pobiera wskaźnik do ciągu reprezentującego Identyfikator tokenu dla subskrypcji `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|Ustawia identyfikator tokenu dla subskrypcji na `IReferenceAppId` wartość określonej wartości ciągu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
- [IEnumReferenceIdentity — Interfejs](ienumreferenceidentity-interface.md)
- [IReferenceIdentity — Interfejs](ireferenceidentity-interface.md)
