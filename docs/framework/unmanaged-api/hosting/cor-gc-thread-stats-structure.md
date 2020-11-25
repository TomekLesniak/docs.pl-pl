---
title: COR_GC_THREAD_STATS — Struktura
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699238"
---
# <a name="cor_gc_thread_stats-structure"></a>COR_GC_THREAD_STATS — Struktura

Zawiera statystyki poszczególnych wątków dotyczące wyrzucania elementów bezużytecznych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`PerThreadAllocation`|Liczba bajtów pamięci przydzieloną w wątku, który jest skojarzony z bieżącym `COR_GC_THREAD_STATS` wystąpieniem. Ta liczba jest wyczyszczona do zera za każdym razem, gdy wystąpi wyrzucanie elementów bezużytecznych generacji.|  
|`Flags`|Liczba bajtów, które mają zostać podwyższone do wyższej generacji przy ostatnim wyrzucaniu elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  

 [ICLRTask:: GetMemStats —](iclrtask-getmemstats-method.md) pobiera parametr wyjściowy typu `COR_GC_THREAD_STATS` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** GCHost. idl  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Struktury](hosting-structures.md)
- [IHostTask — Interfejs](ihosttask-interface.md)
