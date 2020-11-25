---
title: CLR_DEBUGGING_PROCESS_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
ms.openlocfilehash: dd148d23d6e29f03052d3bbf1fcd5d02fb332a0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729853"
---
# <a name="clr_debugging_process_flags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS — Wyliczenie

Dostarcza wartości, które są używane przez metodę [ICLRDebugging:: OpenVirtualProcess —](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|To środowisko uruchomieniowe ma niecatche zarządzane zdarzenie debugera do wysłania. Zapoznaj się z sekcją uwagi w celu rozróżnienia między zdarzeniami przechwytywania i niecatch.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Oczekiwane zdarzenie zarządzane to <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> żądanie.|  
  
## <a name="remarks"></a>Uwagi  

 Zdarzenia dotyczące przechwytywania obejmują proces, domenę aplikacji, zestaw, moduł i powiadomienia o tworzeniu wątku, które umożliwiają debugerowi dostęp do bieżącego stanu po dołączeniu go do procesu. Zdarzenia niecatch, które są wskazywane przez `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flagę, obejmują wszystkie inne zdarzenia debugera, takie jak wyjątki i powiadomienia programu Managed Debug Assistant (MDA).  
  
 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`Flaga włącza środowisko uruchomieniowe, aby odróżnić między wyjątkami kończącymi i żądaniem dołączenia zarządzanego debugera, który można anulować.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. idl, dbhost. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
- [Debugowanie](index.md)
