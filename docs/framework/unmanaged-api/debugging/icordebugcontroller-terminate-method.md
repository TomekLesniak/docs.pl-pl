---
title: ICorDebugController::Terminate — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: 460aeeca9d62ce91a11a24d774c8e681ed4f00ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679809"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate — Metoda

Kończy proces z określonym kodem zakończenia.  
  
> [!NOTE]
> Ta metoda jest otoką dla funkcji Win32 `TerminateProcess` . W tym celu program `Terminate` używa kodu zakończenia w taki sam sposób, w jaki `TerminateProcess` używa go funkcja Win32.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `exitCode`  
 podczas Wartość liczbowa, która jest kodem zakończenia. Prawidłowe wartości liczbowe są zdefiniowane w Winbase. h.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli proces zostanie zatrzymany po `Terminate` wywołaniu, proces powinien być kontynuowany przy użyciu metody [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , aby debuger otrzymał potwierdzenie zakończenia za pośrednictwem wywołania zwrotnego [ICorDebugManagedCallback:: ExitProcess —](icordebugmanagedcallback-exitprocess-method.md) lub [ICorDebugManagedCallback:: ExitAppDomain —](icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Ta metoda nie jest implementowana przez domenę aplikacji. Oznacza to, że nie jest zaimplementowana na <xref:System.AppDomain> poziomie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
