---
title: ICLRIoCompletionManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714123"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager — Interfejs

Implementuje metodę wywołania zwrotnego, która umożliwia hostowi powiadamianie środowiska uruchomieniowego języka wspólnego (CLR) o stanie określonych żądań we/wy.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[OnComplete, metoda](iclriocompletionmanager-oncomplete-method.md)|Powiadamia CLR o stanie żądania we/wy, które zostało wykonane przy użyciu wywołania metody [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Uwagi  

 Host implementuje abstrakcję ukończenia we/wy przy użyciu interfejsu [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . Środowisko CLR wykonuje żądania we/wy za pośrednictwem tego interfejsu, a host powiadamia środowisko uruchomieniowe o wyniku takich żądań za pomocą `ICLRIoCompletionManager` interfejsu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostIoCompletionManager — Interfejs](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager — Interfejs](ihostthreadpoolmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
