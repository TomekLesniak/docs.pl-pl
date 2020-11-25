---
title: ICorDebugStepper::Step — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 234705e4495a1a582f3801ad1e645f923cd6f4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727695"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step — Metoda

Powoduje, że ICorDebugStepper to jeden krok za pomocą zawartego w nim wątku i opcjonalnie, aby kontynuować wykonywanie jednostopniowe za pomocą funkcji, które są wywoływane w wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `bStepIn`  
 podczas Ustaw, aby `true` wkroczyć do funkcji, która jest wywoływana w wątku. Ustaw, aby przekroczyć `false` funkcję.  
  
## <a name="remarks"></a>Uwagi  

 Krok zostaje zakończony, gdy środowisko uruchomieniowe języka wspólnego wykonuje następną zarządzaną instrukcję w tej stepper. Jeśli `Step` jest wywoływana na stepper, który nie jest w kodzie zarządzanym, krok zostanie ukończony, gdy Następna instrukcja kodu zarządzanego zostanie wykonana przez wątek.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
