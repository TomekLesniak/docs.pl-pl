---
title: IHostMalloc — Interfejs
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702163"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc — Interfejs

Zapewnia metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) żądania bardziej szczegółowych alokacji ze sterty za pośrednictwem hosta.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Alloc, metoda](ihostmalloc-alloc-method.md)|Żąda od sterty przydzielenia przez hosta żądaną ilość pamięci.|  
|[DebugAlloc, metoda](ihostmalloc-debugalloc-method.md)|Żąda, aby Host przydzielił żądaną ilość pamięci ze sterty, a także śledzić miejsce przydzielenia pamięci.|  
|[Free, metoda](ihostmalloc-free-method.md)|Zwalnia pamięć przydzieloną przy użyciu `Alloc` metody.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR Pobiera wskaźnik interfejsu do `IHostMalloc` wystąpienia, wywołując metodę [IHostMemoryManager::](ihostmemorymanager-createmalloc-method.md) CreateInstance.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
