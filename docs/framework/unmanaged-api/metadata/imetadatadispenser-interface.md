---
title: IMetaDataDispenser — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: c798aeba46adf91a8c13f8143c00f02173a0bb52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726113"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser — Interfejs

Zawiera metody tworzenia nowego zakresu metadanych lub otwierania istniejącego.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineScope, metoda](imetadatadispenser-definescope-method.md)|Tworzy nowy obszar w pamięci, w którym można tworzyć nowe metadane.|  
|[OpenScope — Metoda](imetadatadispenser-openscope-method.md)|Otwiera istniejący plik na dysku i mapuje jego metadane do pamięci.|  
|[OpenScopeOnMemory, metoda](imetadatadispenser-openscopeonmemory-method.md)|Otwiera obszar pamięci, który zawiera istniejące metadane. Oznacza to, że ta metoda otwiera określony obszar pamięci, w której istniejące dane są traktowane jako metadane.|  
  
## <a name="requirements"></a>Wymagania  

 **Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataDispenserEx — Interfejs](imetadatadispenserex-interface.md)
- [Interfejsy metadanych](metadata-interfaces.md)
