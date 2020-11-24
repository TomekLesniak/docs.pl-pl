---
title: IHostCrst — Interfejs
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 350af708456914c73929d2b8887173cf784d4294
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680563"
---
# <a name="ihostcrst-interface"></a>IHostCrst — Interfejs

Służy jako reprezentacja hosta sekcji krytycznej dla wątków.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Enter, metoda](ihostcrst-enter-method.md)|Wprowadza sekcję krytyczną.|  
|[Leave, metoda](ihostcrst-leave-method.md)|Pozostawia sekcję krytyczną.|  
|[SetSpinCount, metoda](ihostcrst-setspincount-method.md)|Ustawia liczbę obrotów dla sekcji krytycznej.|  
|[TryEnter, metoda](ihostcrst-tryenter-method.md)|Próbuje wprowadzić sekcję krytyczną i natychmiast raportuje powodzenie lub niepowodzenie.|  
  
## <a name="remarks"></a>Uwagi  

 `IHostCrst` zezwala, aby środowisko uruchomieniowe języka wspólnego (CLR) komunikować się bezpośrednio z reprezentacją w sekcji krytycznej hosta, a nie przy użyciu funkcji Win32, takich jak `EnterCriticalSection` lub `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRSyncManager — Interfejs](iclrsyncmanager-interface.md)
- [IHostSyncManager — Interfejs](ihostsyncmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
