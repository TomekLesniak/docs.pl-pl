---
title: ICorDebugStepper::StepOut — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 1396e7a8ca61734a9363a9c852502290675249d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727669"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut — Metoda

Powoduje, że ICorDebugStepper to jeden krok za pomocą zawartego w nim wątku oraz do zakończenia, gdy bieżąca ramka zwraca sterowanie do ramki wywołującej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Uwagi  

 Operacja zakończy `StepOut` się po powrocie z bieżącej ramki do ramki wywołującej.  
  
 Jeśli `StepOut` jest wywoływana w kodzie niezarządzanym, krok zakończy się, gdy bieżąca ramka powróci do zarządzanego kodu, który go wywołał.  
  
 W .NET Framework w wersji 2,0 nie należy używać `StepOut` z ustawioną flagą STOP_UNMANAGED, ponieważ zakończy się niepowodzeniem. (Użyj [ICorDebugStepper:: SetUnmappedStopMask —](icordebugstepper-setunmappedstopmask-method.md) , aby ustawić flagi do wykonywania krokowo). Debugery międzyoperacyjności muszą przekroczyć kod natywny.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
