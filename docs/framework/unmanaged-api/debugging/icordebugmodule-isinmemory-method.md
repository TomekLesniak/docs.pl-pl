---
title: ICorDebugModule::IsInMemory — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709820"
---
# <a name="icordebugmoduleisinmemory-method"></a>ICorDebugModule::IsInMemory — Metoda

Pobiera wartość wskazującą, czy ten moduł istnieje tylko w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pInMemory`  
 [out] `true` Jeśli ten moduł istnieje tylko w pamięci; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Środowisko uruchomieniowe języka wspólnego (CLR) obsługuje ładowanie modułów z nieprzetworzonych strumieni bajtów. Takie moduły są wywoływane *w modułach pamięci* i nie istnieją na dysku.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
