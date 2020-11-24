---
title: IDefinitionAppId — Interfejs
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 1e6c42d8e74d2d3e7925c657c67832f662416e64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673872"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId — Interfejs

Reprezentuje unikatowy identyfikator kodu, który definiuje aplikację w bieżącym zakresie.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Pobiera sformatowany ciąg, który reprezentuje kod w tym `IDefinitionAppId` obiekcie.|  
|`IDefinitionAppId::put_Codebase`|Ustawia kod tego `IDefinitionAppId` obiektu na określoną wartość ciągu sformatowanego.|  
|`IDefinitionAppId::EnumAppPath`|Pobiera wskaźnik interfejsu do obiektu [IEnumDefinitionIdentity —](ienumdefinitionidentity-interface.md) , który zawiera zestawy w bieżącej ścieżce aplikacji.|  
|`IDefinitionAppId::SetAppPath`|Ustawia ścieżkę aplikacji dla zestawu w bieżącym zakresie do wartości, do której odwołuje się określony obiekt [IDefinitionIdentity —](idefinitionidentity-interface.md) .|  
|`IDefinitionAppId::get_SubscriptionId`|Pobiera wskaźnik do ciągu reprezentującego Identyfikator tokenu dla subskrypcji dla tego `IDefinitionAppId` obiektu.|  
|`IDefinitionAppId::put_SubscriptionId`|Ustawia identyfikator tokenu dla subskrypcji dla tego `IDefinitionAppId` obiektu na określoną wartość ciągu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Izolacja. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
