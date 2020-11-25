---
title: IAssemblyName — Interfejs
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715072"
---
# <a name="iassemblyname-interface"></a>IAssemblyName — Interfejs

Zapewnia metody opisujące unikatową tożsamość zestawu i pracę z nim.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Clone — Metoda](iassemblyname-clone-method.md)|Tworzy skróconą kopię tego `IAssemblyName` obiektu.|  
|[Finalize, metoda](iassemblyname-finalize-method.md)|Zezwala temu `IAssemblyName` obiektowi na zwalnianie zasobów i wykonywanie innych operacji czyszczenia przed wywołaniem destruktora.|  
|[GetDisplayName — Metoda](iassemblyname-getdisplayname-method.md)|Pobiera nazwę zestawu, do którego odwołuje się ten `IAssemblyName` obiekt.|  
|[GetName — Metoda](iassemblyname-getname-method.md)|Pobiera prostą, niezaszyfrowaną nazwę zestawu, do którego odwołuje się ten `IAssemblyName` obiekt.|  
|[GetProperty — Metoda](iassemblyname-getproperty-method.md)|Pobiera wskaźnik do właściwości, do której odwołuje się określony `PropertyId` .|  
|[GetVersion — Metoda](iassemblyname-getversion-method.md)|Pobiera informacje o wersji zestawu, do którego odwołuje się ten `IAssemblyName` obiekt.|  
|[IsEqual, metoda](iassemblyname-isequal-method.md)|Określa, czy określony `IAssemblyName` obiekt jest równy temu `IAssemblyName` , na podstawie określonych flag porównania.|  
|[SetProperty, metoda](iassemblyname-setproperty-method.md)|Ustawia wartość właściwości, do której odwołuje się określony `PropertyId` .|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
- [IAssemblyEnum — Interfejs](iassemblyenum-interface.md)
