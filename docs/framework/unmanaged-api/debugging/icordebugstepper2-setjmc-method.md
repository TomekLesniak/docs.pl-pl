---
title: ICorDebugStepper2::SetJMC — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 1bbcbcfbb78d421f247a13f58070b68f701e4ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697223"
---
# <a name="icordebugstepper2setjmc-method"></a>ICorDebugStepper2::SetJMC — Metoda

Ustawia wartość określającą, czy ten ICorDebugStepper czynności tylko za pomocą kodu, który jest tworzony przez dewelopera aplikacji. Ten proces jest również znany jako debugowanie tylko mój kod (JMC).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `fIsJMCStepper`  
 podczas Ustaw na `true` krok tylko za pomocą kodu, który jest tworzony przez dewelopera aplikacji; w przeciwnym razie ustaw wartość `false` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
