---
title: ICorDebugProcess::ModifyLogSwitch — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 3ac1b3606131f534195df9b6b59bf72b1bff27fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724536"
---
# <a name="icordebugprocessmodifylogswitch-method"></a>ICorDebugProcess::ModifyLogSwitch — Metoda

Ustawia poziom ważności określonego przełącznika dziennika.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a>Parametry  

 `pLogSwitchName`  
 podczas Wskaźnik do ciągu, który określa nazwę przełącznika dziennika.  
  
 `lLevel`  
 podczas Poziom ważności, który ma zostać ustawiony dla określonego przełączenia dziennika.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest prawidłowa tylko po wystąpieniu wywołania zwrotnego [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
