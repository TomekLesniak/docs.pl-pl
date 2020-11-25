---
title: ICorDebugStepper::SetUnmappedStopMask — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698757"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask — Metoda

Ustawia wartość określającą typ niezamapowanego kodu, w którym wykonanie zostanie zatrzymane.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `mask`  
 podczas Wartość wyliczenia CorDebugUnmappedStop —, która określa typ niezamapowanego kodu, w którym debuger zostanie zatrzymany.  
  
 Wartość domyślna to STOP_OTHER_UNMAPPED. Wartość STOP_UNMANAGED jest prawidłowa tylko z debugowaniem międzyoperacyjnym.  
  
## <a name="remarks"></a>Uwagi  

 Gdy debuger odnajdzie kompilację just-in-Time (JIT), która nie ma odpowiedniego mapowania do języka pośredniego firmy Microsoft (MSIL), zatrzymuje wykonywanie, jeśli ustawiono flagę, która określa ten typ niezamapowanego kodu; w przeciwnym razie w dalszym ciągu kontynuuje działanie.  
  
 Jeśli debuger nie używa stepper do wprowadzania metody, nie będzie koniecznie przekroczyć niezamapowanego kodu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
