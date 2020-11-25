---
title: EMemoryCriticalLevel — Wyliczenie
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 3b9ad4b40ce94420f2ab5fc25335c41dec15dc09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720558"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel — Wyliczenie

Zawiera wartości wskazujące wpływ błędu w przypadku żądania określonego przydziału pamięci, ale nie można go spełnić.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`eAppDomainCritical`|Wskazuje, że alokacja ma kluczowe znaczenie dla wykonywania kodu zarządzanego w domenie, która zażądała alokacji. Jeśli nie można przydzielić pamięci, środowisko CLR nie może zagwarantować, że domena nadal będzie można używać. Host decyduje, jakie działania należy podjąć, gdy nie można spełnić alokacji. Może nakazać automatyczne przerwanie działania środowiska CLR `AppDomain` lub pozwolić na jego działanie przez wywoływanie metod w [ICLRPolicyManager](iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Wskazuje, że alokacja ma krytyczne znaczenie dla wykonywania kodu zarządzanego w procesie. Ta wartość jest używana podczas uruchamiania i uruchamiania finalizatorów. Jeśli nie można przydzielić pamięci, środowisko CLR nie może działać w procesie. Jeśli alokacja nie powiedzie się, środowisko CLR jest skutecznie wyłączone. Wszystkie kolejne wywołania środowiska CLR kończą się niepowodzeniem z HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Wskazuje, że alokacja ma krytyczne znaczenie dla uruchomienia zadania, które zażądało alokacji. Jeśli nie można przydzielić pamięci, środowisko CLR nie gwarantuje, że zadanie może być wykonane. W przypadku awarii środowisko CLR zgłasza <xref:System.Threading.ThreadAbortException> w wątku fizycznego systemu operacyjnego.|  
  
## <a name="remarks"></a>Uwagi  

 Metody alokacji pamięci zdefiniowane w interfejsach [IHostMemoryManager](ihostmemorymanager-interface.md) i [IHostMAlloc](ihostmalloc-interface.md) przyjmują parametr tego typu. W zależności od wagi błędu host może zdecydować, czy natychmiast przerwać żądanie alokacji, czy czekać, aż będzie można je spełnić.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRMemoryNotificationCallback — Interfejs](iclrmemorynotificationcallback-interface.md)
- [Hosting — Wyliczenia](hosting-enumerations.md)
