---
title: ICorDebugProcess2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: f1a30c197373928ec10c2b84de4e805b94ea2384
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724510"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2, interfejs

Logiczne rozszerzenie interfejsu ICorDebugProcess, które reprezentuje proces z uruchomionym kodem zarządzanym.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint, metoda](icordebugprocess2-clearunmanagedbreakpoint-method.md)|Usuwa punkt przerwania w określonym przesunięciu, który został ustawiony przez wcześniejsze wywołanie do `ICorDebugProcess2::SetUnmanagedBreakpoint` .|  
|[GetDesiredNGENCompilerFlags, metoda](icordebugprocess2-getdesiredngencompilerflags-method.md)|Pobiera flagi, które muszą zostać ustawione dla środowiska uruchomieniowego języka wspólnego (CLR) w celu załadowania obrazu do procesu, do którego się odwołuje `ICorDebugProcess2` .|  
|[GetReferenceValueFromGCHandle, metoda](icordebugprocess2-getreferencevaluefromgchandle-method.md)|Pobiera wskaźnik odwołania do określonego obiektu zarządzanego, który ma dojście do wyrzucania elementów bezużytecznych.|  
|[GetThreadForTaskID, metoda](icordebugprocess2-getthreadfortaskid-method.md)|Pobiera wątek, na którym wykonywane jest zadanie o określonym identyfikatorze.|  
|[GetVersion — Metoda](icordebugprocess2-getversion-method.md)|Pobiera wersję środowiska CLR, na którym jest uruchomiony debugowany proces.|  
|[SetDesiredNGENCompilerFlags, metoda](icordebugprocess2-setdesiredngencompilerflags-method.md)|Ustawia flagi wymagane przez kompilator just-in-Time (JIT) do załadowania obrazu do debugowanego procesu.|  
|[SetUnmanagedBreakpoint, metoda](icordebugprocess2-setunmanagedbreakpoint-method.md)|Ustawia niezarządzany punkt przerwania w określonym przesunięciu obrazu natywnego.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
