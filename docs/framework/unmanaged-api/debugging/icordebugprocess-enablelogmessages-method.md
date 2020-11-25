---
title: ICorDebugProcess::EnableLogMessages — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: 86cb1a2eb18840419d2a4e8ee4f6475edafe8397
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724627"
---
# <a name="icordebugprocessenablelogmessages-method"></a>ICorDebugProcess::EnableLogMessages — Metoda

Włącza i wyłącza przekazywanie komunikatów dziennika do debugera.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a>Parametry  

 `fOnOff`  
 [w] `true` Włącza transmisję komunikatów dziennika; `false` wyłącza przesyłanie.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest prawidłowa tylko po wywołaniu wywołania zwrotnego [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
