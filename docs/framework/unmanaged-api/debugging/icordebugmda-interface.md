---
title: ICorDebugMDA — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710847"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA — Interfejs

Reprezentuje komunikat asystenta zarządzanego debugowania (MDA).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetDescription, metoda](icordebugmda-getdescription-method.md)|Pobiera ciąg zawierający opis tego elementu MDA.|  
|[GetFlags, metoda](icordebugmda-getflags-method.md)|Pobiera flagi skojarzone z tym zdarzeniem MDA.|  
|[GetName — Metoda](icordebugmda-getname-method.md)|Pobiera ciąg zawierający nazwę tego elementu MDA.|  
|[GetOSThreadId, metoda](icordebugmda-getosthreadid-method.md)|Pobiera identyfikator wątku systemu operacyjnego, na którym jest wykonywane zdarzenie MDA.|  
|[GetXML, metoda](icordebugmda-getxml-method.md)|Pobiera pełny strumień XML skojarzony z tym MDA.|  
  
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
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
