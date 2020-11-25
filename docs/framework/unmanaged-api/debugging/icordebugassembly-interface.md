---
title: ICorDebugAssembly, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: 821eae8ea5b4147408e9fe60d1e5b70c7936959e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696248"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly, interfejs

Reprezentuje zestaw.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EnumerateModules, metoda](icordebugassembly-enumeratemodules-method.md)|Pobiera moduł wyliczający dla modułów zawartych w zestawie.|  
|[GetAppDomain, metoda](icordebugassembly-getappdomain-method.md)|Pobiera wskaźnik interfejsu do domeny aplikacji, która zawiera to `ICorDebugAssembly` wystąpienie.|  
|[GetCodeBase, metoda](icordebugassembly-getcodebase-method.md)|Nie zaimplementowane w bieżącej wersji .NET Framework.|  
|[GetName — Metoda](icordebugassembly-getname-method.md)|Pobiera nazwę zestawu.|  
|[GetProcess — Metoda](icordebugassembly-getprocess-method.md)|Pobiera wystąpienie ICorDebugProcess, w którym jest uruchomiony zestaw.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
