---
title: IReferenceIdentity — Interfejs
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704555"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity — Interfejs

Reprezentuje odwołanie do unikatowego podpisu obiektu kodu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Pobiera wskaźnik interfejsu do nowego `IReferenceIdentity` wystąpienia, które jest identyczne z tą `IReferenceIdentity` różnicą, z wyjątkiem określonych zmian atrybutów.|  
|`IReferenceIdentity::EnumAttributes`|Pobiera wskaźnik interfejsu do `IEnumIDENTITY_ATTRIBUTE` wystąpienia, które zawiera atrybuty skojarzone z tym elementem `IReferenceIdentity` .|  
|`IReferenceIdentity::GetAttribute`|Pobiera wartość atrybutu w określonym obszarze nazw z określoną nazwą.|  
|`IReferenceIdentity::SetAttribute`|Ustawia atrybut, który ma określoną przestrzeń nazw i określoną nazwę określonej wartości.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE — Interfejs](ienumidentity-attribute-interface.md)
