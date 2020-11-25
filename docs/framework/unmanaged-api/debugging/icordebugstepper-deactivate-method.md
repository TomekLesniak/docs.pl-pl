---
title: ICorDebugStepper::Deactivate — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730594"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate — Metoda

Powoduje anulowanie przez ten ICorDebugStepper polecenia ostatniego kroku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Uwagi  

 Nowe polecenie krokowe może zostać wydane po anulowaniu niedawno otrzymanego kroku polecenia.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
