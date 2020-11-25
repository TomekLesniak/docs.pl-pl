---
title: IHostThreadPoolManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: b6625b0ef4dc3de4067514a0b39849c7a958d5c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730763"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager — Interfejs

Dostarcza metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) do konfigurowania puli wątków i umieszczania elementów roboczych w kolejce w puli wątków.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetAvailableThreads, metoda](ihostthreadpoolmanager-getavailablethreads-method.md)|Pobiera liczbę wątków w puli wątków, które nie przetwarzają obecnie elementów roboczych.|  
|[GetMaxThreads, metoda](ihostthreadpoolmanager-getmaxthreads-method.md)|Pobiera maksymalną liczbę wątków, które Host przechowuje współbieżnie w puli wątków.|  
|[GetMinThreads, metoda](ihostthreadpoolmanager-getminthreads-method.md)|Pobiera minimalną liczbę bezczynnych wątków hostowanych przez hosta w oczekiwaniu na żądania.|  
|[QueueUserWorkItem, metoda](ihostthreadpoolmanager-queueuserworkitem-method.md)|Kolejkuje funkcję do wykonania i dostarcza obiekt zawierający dane, które mają być używane przez funkcję.|  
|[SetMaxThreads, metoda](ihostthreadpoolmanager-setmaxthreads-method.md)|Ustawia maksymalną liczbę wątków, które host może przechowywać w puli wątków.|  
|[SetMinThreads, metoda](ihostthreadpoolmanager-setminthreads-method.md)|Określa minimalną liczbę bezczynnych wątków, które host musi zachować w oczekiwaniu na żądania.|  
  
## <a name="remarks"></a>Uwagi  

 Host nie jest wymagany do skonfigurowania puli wątków przy użyciu wartości określonych w wywołaniach `SetMaxThreads` `SetMinThreads` metod i. W takim przypadku host powinien zwrócić wartość HRESULT E_NOTIMPL z tych metod.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Hosting — Interfejsy](hosting-interfaces.md)
