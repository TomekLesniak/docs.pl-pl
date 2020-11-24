---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 386f975ab0bbbe804fda2bd7567acf24f69e77fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676078"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions — Metoda

Wylicza określone obszary pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `callback`  
 podczas Wskaźnik do wystąpienia [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) , który jest wywoływany przez tę metodę dla każdego regionu pamięci, który jest wyliczany w celu powiadomienia debugera wyniku.  
  
 Wyliczenie regionów pamięci jest kontynuowane nawet wtedy, gdy wywołanie zwrotne wskazuje na błąd.  
  
 `miniDumpFlags`  
 podczas Nieużywane.  
  
 `clrFlags`  
 podczas Wartość wyliczenia [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) , która określa regiony pamięci do wyliczenia.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda używa określonego wystąpienia [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) do powiadomienia obiektu wywołującego wyniki.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRDataEnumMemoryRegions — Interfejs](iclrdataenummemoryregions-interface.md)
